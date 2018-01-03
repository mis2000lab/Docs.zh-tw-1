---
uid: mvc/overview/older-versions-1/controllers-and-routing/improving-performance-with-output-caching-cs
title: "改善效能與輸出快取 (C#) |Microsoft 文件"
author: microsoft
description: "在此教學課程中，您學會如何您可以大幅改善效能的 ASP.NET MVC web 應用程式藉由運用輸出快取。 您..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 01/27/2009
ms.topic: article
ms.assetid: 521c9117-81cd-4d8d-9d96-0256dc7bf50f
ms.technology: dotnet-mvc
ms.prod: .net-framework
msc.legacyurl: /mvc/overview/older-versions-1/controllers-and-routing/improving-performance-with-output-caching-cs
msc.type: authoredcontent
ms.openlocfilehash: 47f0aa976c5876991ccc2406fb8f7402e59ec556
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2017
---
<a name="improving-performance-with-output-caching-c"></a><span data-ttu-id="893a8-104">使用輸出快取 (C#) 改善效能</span><span class="sxs-lookup"><span data-stu-id="893a8-104">Improving Performance with Output Caching (C#)</span></span>
====================
<span data-ttu-id="893a8-105">由[Microsoft](https://github.com/microsoft)</span><span class="sxs-lookup"><span data-stu-id="893a8-105">by [Microsoft](https://github.com/microsoft)</span></span>

> <span data-ttu-id="893a8-106">在此教學課程中，您學會如何您可以大幅改善效能的 ASP.NET MVC web 應用程式藉由運用輸出快取。</span><span class="sxs-lookup"><span data-stu-id="893a8-106">In this tutorial, you learn how you can dramatically improve the performance of your ASP.NET MVC web applications by taking advantage of output caching.</span></span> <span data-ttu-id="893a8-107">您了解如何快取，因此相同的內容不需要建立新的使用者叫用的動作，每次從控制器動作傳回的結果。</span><span class="sxs-lookup"><span data-stu-id="893a8-107">You learn how to cache the result returned from a controller action so that the same content does not need to be created each and every time a new user invokes the action.</span></span>


<span data-ttu-id="893a8-108">本教學課程的目標是以說明您如何可以大幅改進 ASP.NET MVC 應用程式的效能利用輸出快取。</span><span class="sxs-lookup"><span data-stu-id="893a8-108">The goal of this tutorial is to explain how you can dramatically improve the performance of an ASP.NET MVC application by taking advantage of the output cache.</span></span> <span data-ttu-id="893a8-109">輸出快取可讓您快取由控制器動作傳回的內容。</span><span class="sxs-lookup"><span data-stu-id="893a8-109">The output cache enables you to cache the content returned by a controller action.</span></span> <span data-ttu-id="893a8-110">這樣一來，相同的內容並不需要在每次叫用相同的控制器動作產生。</span><span class="sxs-lookup"><span data-stu-id="893a8-110">That way, the same content does not need to be generated each and every time the same controller action is invoked.</span></span>

<span data-ttu-id="893a8-111">例如，假設 ASP.NET MVC 應用程式，會在名為索引檢視中顯示資料庫記錄的清單。</span><span class="sxs-lookup"><span data-stu-id="893a8-111">Imagine, for example, that your ASP.NET MVC application displays a list of database records in a view named Index.</span></span> <span data-ttu-id="893a8-112">一般來說，每個使用者叫用傳回的索引檢視中，控制器動作的時間的資料庫記錄集必須擷取從資料庫執行資料庫查詢。</span><span class="sxs-lookup"><span data-stu-id="893a8-112">Normally, each and every time that a user invokes the controller action that returns the Index view, the set of database records must be retrieved from the database by executing a database query.</span></span>

<span data-ttu-id="893a8-113">如果您充分利用輸出快取的相反地，您可以避免執行資料庫查詢，每次任何使用者叫用相同的控制器動作。</span><span class="sxs-lookup"><span data-stu-id="893a8-113">If, on the other hand, you take advantage of the output cache then you can avoid executing a database query every time any user invokes the same controller action.</span></span> <span data-ttu-id="893a8-114">檢視可以擷取從快取，而不是從控制器動作正在重新產生。</span><span class="sxs-lookup"><span data-stu-id="893a8-114">The view can be retrieved from the cache instead of being regenerated from the controller action.</span></span> <span data-ttu-id="893a8-115">您可以避免執行重複快取可讓在伺服器上運作。</span><span class="sxs-lookup"><span data-stu-id="893a8-115">Caching enables you to avoid performing redundant work on the server.</span></span>

## <a name="enabling-output-caching"></a><span data-ttu-id="893a8-116">啟用輸出快取</span><span class="sxs-lookup"><span data-stu-id="893a8-116">Enabling Output Caching</span></span>

<span data-ttu-id="893a8-117">您可以啟用輸出快取加入至個別的控制器動作或整個控制器類別 [OutputCache] 屬性。</span><span class="sxs-lookup"><span data-stu-id="893a8-117">You enable output caching by adding an [OutputCache] attribute to either an individual controller action or an entire controller class.</span></span> <span data-ttu-id="893a8-118">例如，列表 1 中的控制站會公開名為 index （） 的動作。</span><span class="sxs-lookup"><span data-stu-id="893a8-118">For example, the controller in Listing 1 exposes an action named Index().</span></span> <span data-ttu-id="893a8-119">Index 動作的輸出快取 10 秒。</span><span class="sxs-lookup"><span data-stu-id="893a8-119">The output of the Index() action is cached for 10 seconds.</span></span>

<span data-ttu-id="893a8-120">**列出 1 – Controllers\HomeController.cs**</span><span class="sxs-lookup"><span data-stu-id="893a8-120">**Listing 1 – Controllers\HomeController.cs**</span></span>

[!code-csharp[Main](improving-performance-with-output-caching-cs/samples/sample1.cs)]

<span data-ttu-id="893a8-121">ASP.NET MVC 的 Beta 版本，在輸出快取不適用於 URL，例如[http://www.MySite.com/](http://www.mysite.com/)。</span><span class="sxs-lookup"><span data-stu-id="893a8-121">In the Beta versions of ASP.NET MVC, output caching does not work for a URL like [http://www.MySite.com/](http://www.mysite.com/).</span></span> <span data-ttu-id="893a8-122">相反地，您必須輸入 URL，例如[http://www.MySite.com/Home/Index](http://www.mysite.com/Home/Index)。</span><span class="sxs-lookup"><span data-stu-id="893a8-122">Instead, you must enter a URL like [http://www.MySite.com/Home/Index](http://www.mysite.com/Home/Index).</span></span> 

<span data-ttu-id="893a8-123">在清單 1 中，index （） 動作的輸出快取 10 秒。</span><span class="sxs-lookup"><span data-stu-id="893a8-123">In Listing 1, the output of the Index() action is cached for 10 seconds.</span></span> <span data-ttu-id="893a8-124">如果您想要的話，您可以指定較長的快取持續時間。</span><span class="sxs-lookup"><span data-stu-id="893a8-124">If you prefer, you can specify a much longer cache duration.</span></span> <span data-ttu-id="893a8-125">例如，如果您想要快取輸出的控制器動作，一天然後您可以指定快取持續時間為 86400 秒 (60 秒\*60 分鐘\*24 小時)。</span><span class="sxs-lookup"><span data-stu-id="893a8-125">For example, if you want to cache the output of a controller action for one day then you can specify a cache duration of 86400 seconds (60 seconds \* 60 minutes \* 24 hours).</span></span>

<span data-ttu-id="893a8-126">沒有內容也不保證會被快取，您指定的時間長度。</span><span class="sxs-lookup"><span data-stu-id="893a8-126">There is no guarantee that content will be cached for the amount of time that you specify.</span></span> <span data-ttu-id="893a8-127">當記憶體資源不足時，快取會自動啟動收回的內容。</span><span class="sxs-lookup"><span data-stu-id="893a8-127">When memory resources become low, the cache starts evicting content automatically.</span></span>

<span data-ttu-id="893a8-128">主控制器清單 1 中的傳回列表 2 中的索引檢視。</span><span class="sxs-lookup"><span data-stu-id="893a8-128">The Home controller in Listing 1 returns the Index view in Listing 2.</span></span> <span data-ttu-id="893a8-129">沒有特殊這份檢視相關的項目。</span><span class="sxs-lookup"><span data-stu-id="893a8-129">There is nothing special about this view.</span></span> <span data-ttu-id="893a8-130">索引檢視只會顯示目前的時間 （請參閱圖 1）。</span><span class="sxs-lookup"><span data-stu-id="893a8-130">The Index view simply displays the current time (see Figure 1).</span></span>

<span data-ttu-id="893a8-131">**列出 2 – Views\Home\Index.aspx**</span><span class="sxs-lookup"><span data-stu-id="893a8-131">**Listing 2 – Views\Home\Index.aspx**</span></span>

[!code-aspx[Main](improving-performance-with-output-caching-cs/samples/sample2.aspx)]

<span data-ttu-id="893a8-132">**圖 1 – 快取索引檢視**</span><span class="sxs-lookup"><span data-stu-id="893a8-132">**Figure 1 – Cached Index view**</span></span>

![clip_image002](improving-performance-with-output-caching-cs/_static/image1.jpg)

<span data-ttu-id="893a8-134">如果您叫用的 index 動作多次在您的瀏覽器的網址列中輸入 URL /Home/索引和重複叫用您的瀏覽器中的 [重新整理/重新載入] 按鈕，然後索引檢視所顯示的時間不會變更為 10 秒。</span><span class="sxs-lookup"><span data-stu-id="893a8-134">If you invoke the Index() action multiple times by entering the URL /Home/Index in the address bar of your browser and hitting the Refresh/Reload button in your browser repeatedly, then the time displayed by the Index view won't change for 10 seconds.</span></span> <span data-ttu-id="893a8-135">因為此檢視會快取，會顯示相同的時間。</span><span class="sxs-lookup"><span data-stu-id="893a8-135">The same time is displayed because the view is cached.</span></span>

<span data-ttu-id="893a8-136">請務必了解每一位使用者造訪您的應用程式相同的檢視，會快取。</span><span class="sxs-lookup"><span data-stu-id="893a8-136">It is important to understand that the same view is cached for everyone who visits your application.</span></span> <span data-ttu-id="893a8-137">叫用 index （） 的動作的任何人會收到相同的快取的版本的索引檢視。</span><span class="sxs-lookup"><span data-stu-id="893a8-137">Anyone who invokes the Index() action will get the same cached version of the Index view.</span></span> <span data-ttu-id="893a8-138">這表示 web 伺服器必須執行來處理索引檢視的工作數量就能大幅降低。</span><span class="sxs-lookup"><span data-stu-id="893a8-138">This means that the amount of work that the web server must perform to serve the Index view is dramatically reduced.</span></span>

<span data-ttu-id="893a8-139">列出 2 中的檢視會做的動作非常簡單的項目。</span><span class="sxs-lookup"><span data-stu-id="893a8-139">The view in Listing 2 happens to be doing something really simple.</span></span> <span data-ttu-id="893a8-140">檢視只會顯示目前的時間。</span><span class="sxs-lookup"><span data-stu-id="893a8-140">The view just displays the current time.</span></span> <span data-ttu-id="893a8-141">不過，您可以如同輕鬆地快取顯示一組資料庫記錄的檢視。</span><span class="sxs-lookup"><span data-stu-id="893a8-141">However, you could just as easily cache a view that displays a set of database records.</span></span> <span data-ttu-id="893a8-142">在此情況下，資料庫中的記錄組會不需要從資料庫擷取，每次叫用傳回檢視的控制器動作。</span><span class="sxs-lookup"><span data-stu-id="893a8-142">In that case, the set of database records would not need to be retrieved from the database each and every time the controller action that returns the view is invoked.</span></span> <span data-ttu-id="893a8-143">快取可以減少您的 web 伺服器和資料庫伺服器必須執行的工作數量。</span><span class="sxs-lookup"><span data-stu-id="893a8-143">Caching can reduce the amount of work that both your web server and database server must perform.</span></span>

<span data-ttu-id="893a8-144">不使用頁面&lt;%@ OutputCache %&gt; MVC 檢視中的指示詞。</span><span class="sxs-lookup"><span data-stu-id="893a8-144">Don't use the page &lt;%@ OutputCache %&gt; directive in an MVC view.</span></span> <span data-ttu-id="893a8-145">這個指示詞透過從 Web Form 世界滴墨-並不能用於 ASP.NET MVC 應用程式。</span><span class="sxs-lookup"><span data-stu-id="893a8-145">This directive is bleeding over from the Web Forms world and should not be used in an ASP.NET MVC application.</span></span>

## <a name="where-content-is-cached"></a><span data-ttu-id="893a8-146">快取內容</span><span class="sxs-lookup"><span data-stu-id="893a8-146">Where Content is Cached</span></span>

<span data-ttu-id="893a8-147">根據預設，當您使用 [OutputCache] 屬性中，內容會快取中三個位置： 網頁伺服器、 任何 proxy 伺服器及網頁瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="893a8-147">By default, when you use the [OutputCache] attribute, content is cached in three locations: the web server, any proxy servers, and the web browser.</span></span> <span data-ttu-id="893a8-148">您可以控制完全內容快取所在藉由修改 [OutputCache] 屬性的 Location 屬性。</span><span class="sxs-lookup"><span data-stu-id="893a8-148">You can control exactly where content is cached by modifying the Location property of the [OutputCache] attribute.</span></span>

<span data-ttu-id="893a8-149">您可以將 [位置] 屬性為下列值之一：</span><span class="sxs-lookup"><span data-stu-id="893a8-149">You can set the Location property to any one of the following values:</span></span>

> <span data-ttu-id="893a8-150">·任何</span><span class="sxs-lookup"><span data-stu-id="893a8-150">· Any</span></span>
> 
> <span data-ttu-id="893a8-151">·用戶端</span><span class="sxs-lookup"><span data-stu-id="893a8-151">· Client</span></span>
> 
> <span data-ttu-id="893a8-152">·下游</span><span class="sxs-lookup"><span data-stu-id="893a8-152">· Downstream</span></span>
> 
> <span data-ttu-id="893a8-153">·伺服器</span><span class="sxs-lookup"><span data-stu-id="893a8-153">· Server</span></span>
> 
> <span data-ttu-id="893a8-154">·無</span><span class="sxs-lookup"><span data-stu-id="893a8-154">· None</span></span>
> 
> <span data-ttu-id="893a8-155">·ServerAndClient</span><span class="sxs-lookup"><span data-stu-id="893a8-155">· ServerAndClient</span></span>


<span data-ttu-id="893a8-156">根據預設，[位置] 屬性任何具有值。</span><span class="sxs-lookup"><span data-stu-id="893a8-156">By default, the Location property has the value Any.</span></span> <span data-ttu-id="893a8-157">不過，有很多情況下您可以只在瀏覽器上，或只能在伺服器上的快取。</span><span class="sxs-lookup"><span data-stu-id="893a8-157">However, there are situations in which you might want to cache only on the browser or only on the server.</span></span> <span data-ttu-id="893a8-158">例如，如果您要快取的每位使用者個人化的資訊然後您應該快取伺服器上的資訊。</span><span class="sxs-lookup"><span data-stu-id="893a8-158">For example, if you are caching information that is personalized for each user then you should not cache the information on the server.</span></span> <span data-ttu-id="893a8-159">如果您要顯示不同的資訊給不同的使用者接著您應該快取只會在用戶端上的資訊。</span><span class="sxs-lookup"><span data-stu-id="893a8-159">If you are displaying different information to different users then you should cache the information only on the client.</span></span>

<span data-ttu-id="893a8-160">例如，列表 3 中的控制站會公開名為 GetName() 傳回目前的使用者名稱的動作。</span><span class="sxs-lookup"><span data-stu-id="893a8-160">For example, the controller in Listing 3 exposes an action named GetName() that returns the current user name.</span></span> <span data-ttu-id="893a8-161">如果插頭登入網站，並叫用 GetName() 動作然後動作會傳回字串"Hi 端子"。</span><span class="sxs-lookup"><span data-stu-id="893a8-161">If Jack logs into the website and invokes the GetName() action then the action returns the string "Hi Jack".</span></span> <span data-ttu-id="893a8-162">如果接下來，Jill 登入網站，並叫用 GetName() 動作然後她也會取得字串"Hi 端子"。</span><span class="sxs-lookup"><span data-stu-id="893a8-162">If, subsequently, Jill logs into the website and invokes the GetName() action then she also will get the string "Hi Jack".</span></span> <span data-ttu-id="893a8-163">字串會針對所有使用者在網頁伺服器上快取的後端子一開始會叫用控制器的動作。</span><span class="sxs-lookup"><span data-stu-id="893a8-163">The string is cached on the web server for all users after Jack initially invokes the controller action.</span></span>

<span data-ttu-id="893a8-164">**列出 3 – Controllers\BadUserController.cs**</span><span class="sxs-lookup"><span data-stu-id="893a8-164">**Listing 3 – Controllers\BadUserController.cs**</span></span>

[!code-csharp[Main](improving-performance-with-output-caching-cs/samples/sample3.cs)]

<span data-ttu-id="893a8-165">最有可能列表 3 中的控制站無法您想要的方式。</span><span class="sxs-lookup"><span data-stu-id="893a8-165">Most likely, the controller in Listing 3 does not work the way that you want.</span></span> <span data-ttu-id="893a8-166">您不想顯示"Hi 端子 」 訊息給 Jill。</span><span class="sxs-lookup"><span data-stu-id="893a8-166">You don't want to display the message "Hi Jack" to Jill.</span></span>

<span data-ttu-id="893a8-167">您應該永遠不會快取伺服器快取中的個人化的內容。</span><span class="sxs-lookup"><span data-stu-id="893a8-167">You should never cache personalized content in the server cache.</span></span> <span data-ttu-id="893a8-168">不過，您可能想要快取個人化的內容，在瀏覽器快取以改善效能。</span><span class="sxs-lookup"><span data-stu-id="893a8-168">However, you might want to cache the personalized content in the browser cache to improve performance.</span></span> <span data-ttu-id="893a8-169">如果您快取內容，在瀏覽器中，而且使用者叫用相同的控制器動作數次，內容可以擷取從瀏覽器快取，而非伺服器。</span><span class="sxs-lookup"><span data-stu-id="893a8-169">If you cache content in the browser, and a user invokes the same controller action multiple times, then the content can be retrieved from the browser cache instead of the server.</span></span>

<span data-ttu-id="893a8-170">修改的控制器中列出的 4 會快取 GetName() 動作的輸出。</span><span class="sxs-lookup"><span data-stu-id="893a8-170">The modified controller in Listing 4 caches the output of the GetName() action.</span></span> <span data-ttu-id="893a8-171">不過，只有瀏覽器和伺服器上不會快取內容。</span><span class="sxs-lookup"><span data-stu-id="893a8-171">However, the content is cached only on the browser and not on the server.</span></span> <span data-ttu-id="893a8-172">這樣一來，當多位使用者叫用 GetName() 方法時，每位人員取得自己的使用者名稱和不可為另一個人的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="893a8-172">That way, when multiple users invoke the GetName() method, each person gets their own user name and not another person's user name.</span></span>

<span data-ttu-id="893a8-173">**列出 4 – Controllers\UserController.cs**</span><span class="sxs-lookup"><span data-stu-id="893a8-173">**Listing 4 – Controllers\UserController.cs**</span></span>

[!code-csharp[Main](improving-performance-with-output-caching-cs/samples/sample4.cs)]

<span data-ttu-id="893a8-174">請注意 [OutputCache] 屬性中列出的 4 包含設定為值 OutputCacheLocation.Client Location 屬性。</span><span class="sxs-lookup"><span data-stu-id="893a8-174">Notice that the [OutputCache] attribute in Listing 4 includes a Location property set to the value OutputCacheLocation.Client.</span></span> <span data-ttu-id="893a8-175">[OutputCache] 屬性也包含 NoStore 屬性。</span><span class="sxs-lookup"><span data-stu-id="893a8-175">The [OutputCache] attribute also includes a NoStore property.</span></span> <span data-ttu-id="893a8-176">NoStore 屬性用來通知 proxy 伺服器與瀏覽器，它們不應該儲存快取內容的永久複本。</span><span class="sxs-lookup"><span data-stu-id="893a8-176">The NoStore property is used to inform proxy servers and browser that they should not store a permanent copy of the cached content.</span></span>

## <a name="varying-the-output-cache"></a><span data-ttu-id="893a8-177">不同的輸出快取</span><span class="sxs-lookup"><span data-stu-id="893a8-177">Varying the Output Cache</span></span>

<span data-ttu-id="893a8-178">在某些情況下，您可以使用不同的快取的版本的完全相同的內容。</span><span class="sxs-lookup"><span data-stu-id="893a8-178">In some situations, you might want different cached versions of the very same content.</span></span> <span data-ttu-id="893a8-179">例如，假設您要建立主要/詳細資料頁面。</span><span class="sxs-lookup"><span data-stu-id="893a8-179">Imagine, for example, that you are creating a master/detail page.</span></span> <span data-ttu-id="893a8-180">主版頁面會顯示一份電影標題。</span><span class="sxs-lookup"><span data-stu-id="893a8-180">The master page displays a list of movie titles.</span></span> <span data-ttu-id="893a8-181">當您按一下標題時，您會取得詳細資訊，針對選取的影片。</span><span class="sxs-lookup"><span data-stu-id="893a8-181">When you click a title, you get details for the selected movie.</span></span>

<span data-ttu-id="893a8-182">如果您要快取的詳細資料頁面，然後相同的電影的詳細資料隨即出現的電影不論您按一下。</span><span class="sxs-lookup"><span data-stu-id="893a8-182">If you cache the details page, then the details for the same movie will be displayed no matter which movie you click.</span></span> <span data-ttu-id="893a8-183">未來的所有使用者，將會顯示第一個使用者所選的第一部電影。</span><span class="sxs-lookup"><span data-stu-id="893a8-183">The first movie selected by the first user will be displayed to all future users.</span></span>

<span data-ttu-id="893a8-184">您可以利用 [OutputCache] 屬性的 VaryByParam 屬性來解決這個問題。</span><span class="sxs-lookup"><span data-stu-id="893a8-184">You can fix this problem by taking advantage of the VaryByParam property of the [OutputCache] attribute.</span></span> <span data-ttu-id="893a8-185">這個屬性可讓您建立不同的快取的版本的完全相同的內容時的表單參數或查詢字串參數而有所不同。</span><span class="sxs-lookup"><span data-stu-id="893a8-185">This property enables you to create different cached versions of the very same content when a form parameter or query string parameter varies.</span></span>

<span data-ttu-id="893a8-186">例如，列出 5 中的控制站會公開兩個名為 Master() 和 Details() 的動作。</span><span class="sxs-lookup"><span data-stu-id="893a8-186">For example, the controller in Listing 5 exposes two actions named Master() and Details().</span></span> <span data-ttu-id="893a8-187">Master() 動作將會傳回一份電影標題及 Details() 動作將會傳回選取的影片的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="893a8-187">The Master() action returns a list of movie titles and the Details() action returns the details for the selected movie.</span></span>

<span data-ttu-id="893a8-188">**列出 5 – Controllers\MoviesController.cs**</span><span class="sxs-lookup"><span data-stu-id="893a8-188">**Listing 5 – Controllers\MoviesController.cs**</span></span>

[!code-csharp[Main](improving-performance-with-output-caching-cs/samples/sample5.cs)]

<span data-ttu-id="893a8-189">Master() 動作包括 VaryByParam 屬性的值"none"。</span><span class="sxs-lookup"><span data-stu-id="893a8-189">The Master() action includes a VaryByParam property with the value "none".</span></span> <span data-ttu-id="893a8-190">當叫用動作時的 Master() 相同快取版本的主要檢視會傳回。</span><span class="sxs-lookup"><span data-stu-id="893a8-190">When the Master() action is invoked, the same cached version of the Master view is returned.</span></span> <span data-ttu-id="893a8-191">參數是任何形式的參數或查詢字串忽略 （請參閱圖 2）。</span><span class="sxs-lookup"><span data-stu-id="893a8-191">Any form parameters or query string parameters are ignored (see Figure 2).</span></span>

<span data-ttu-id="893a8-192">**圖 2 – /Movies/Master 檢視**</span><span class="sxs-lookup"><span data-stu-id="893a8-192">**Figure 2 – The /Movies/Master view**</span></span>

![clip_image004](improving-performance-with-output-caching-cs/_static/image2.jpg)

<span data-ttu-id="893a8-194">**圖 3 – / 電影/詳細資料檢視**</span><span class="sxs-lookup"><span data-stu-id="893a8-194">**Figure 3 – The /Movies/Details view**</span></span>

![clip_image006](improving-performance-with-output-caching-cs/_static/image3.jpg)

<span data-ttu-id="893a8-196">Details() 動作包括 VaryByParam 屬性與值 「 識別碼 」。</span><span class="sxs-lookup"><span data-stu-id="893a8-196">The Details() action includes a VaryByParam property with the value "Id".</span></span> <span data-ttu-id="893a8-197">不同的 Id 參數的值傳遞至控制器動作，都會產生不同的快取的版本的詳細資料檢視。</span><span class="sxs-lookup"><span data-stu-id="893a8-197">When different values of the Id parameter are passed to the controller action, different cached versions of the Details view are generated.</span></span>

<span data-ttu-id="893a8-198">它是一定要了解使用的 VaryByParam 屬性會導致多個快取，且不小於。</span><span class="sxs-lookup"><span data-stu-id="893a8-198">It is important to understand that using the VaryByParam property results in more caching and not less.</span></span> <span data-ttu-id="893a8-199">不同的快取的版本的詳細資料檢視會建立每個不同版本的識別碼參數。</span><span class="sxs-lookup"><span data-stu-id="893a8-199">A different cached version of the Details view is created for each different version of the Id parameter.</span></span>

<span data-ttu-id="893a8-200">您可以設定 VaryByParam 屬性為下列值：</span><span class="sxs-lookup"><span data-stu-id="893a8-200">You can set the VaryByParam property to the following values:</span></span>

> <span data-ttu-id="893a8-201">\*= 表單或查詢字串參數而有所不同時，請建立不同的快取的版本。</span><span class="sxs-lookup"><span data-stu-id="893a8-201">\* = Create a different cached version whenever a form or query string parameter varies.</span></span>
> 
> <span data-ttu-id="893a8-202">none = 永不建立不同的快取的版本</span><span class="sxs-lookup"><span data-stu-id="893a8-202">none = Never create different cached versions</span></span>
> 
> <span data-ttu-id="893a8-203">以分號的參數清單 = 建立不同的快取的版本，只要在清單中的表單或查詢字串參數的任何變化</span><span class="sxs-lookup"><span data-stu-id="893a8-203">Semicolon list of parameters = Create different cached versions whenever any of the form or query string parameters in the list varies</span></span>


## <a name="creating-a-cache-profile"></a><span data-ttu-id="893a8-204">建立快取設定檔</span><span class="sxs-lookup"><span data-stu-id="893a8-204">Creating a Cache Profile</span></span>

<span data-ttu-id="893a8-205">藉由修改 [OutputCache] 屬性的屬性來設定輸出快取屬性的替代方案，您可以建立 web 組態檔 (web.config) 中快取設定檔。</span><span class="sxs-lookup"><span data-stu-id="893a8-205">As an alternative to configuring output cache properties by modifying properties of the [OutputCache] attribute, you can create a cache profile in the web configuration (web.config) file.</span></span> <span data-ttu-id="893a8-206">在 web 組態檔中建立快取設定檔提供了幾個重要的優點。</span><span class="sxs-lookup"><span data-stu-id="893a8-206">Creating a cache profile in the web configuration file offers a couple of important advantages.</span></span>

<span data-ttu-id="893a8-207">首先，藉由設定輸出快取 web 組態檔中，您可以控制如何控制器動作快取在單一集中位置的內容。</span><span class="sxs-lookup"><span data-stu-id="893a8-207">First, by configuring output caching in the web configuration file, you can control how controller actions cache content in one central location.</span></span> <span data-ttu-id="893a8-208">您可以建立一個快取設定檔，並將設定檔套用至數個控制站或控制器的動作。</span><span class="sxs-lookup"><span data-stu-id="893a8-208">You can create one cache profile and apply the profile to several controllers or controller actions.</span></span>

<span data-ttu-id="893a8-209">第二，您可以修改 web 組態檔不需要重新編譯您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="893a8-209">Second, you can modify the web configuration file without recompiling your application.</span></span> <span data-ttu-id="893a8-210">如果您需要停用快取的應用程式已經部署到生產環境，您可以只修改 web 組態檔中定義的快取設定檔。</span><span class="sxs-lookup"><span data-stu-id="893a8-210">If you need to disable caching for an application that has already been deployed to production, then you can simply modify the cache profiles defined in the web configuration file.</span></span> <span data-ttu-id="893a8-211">Web 組態檔的任何變更將會自動偵測並套用。</span><span class="sxs-lookup"><span data-stu-id="893a8-211">Any changes to the web configuration file will be detected automatically and applied.</span></span>

<span data-ttu-id="893a8-212">例如，&lt;快取&gt;列出 6 中的 web 組態區段會定義名為 Cache1Hour 快取設定檔。</span><span class="sxs-lookup"><span data-stu-id="893a8-212">For example, the &lt;caching&gt; web configuration section in Listing 6 defines a cache profile named Cache1Hour.</span></span> <span data-ttu-id="893a8-213">&lt;快取&gt;區段必須出現在&lt;system.web&gt; web 組態檔區段。</span><span class="sxs-lookup"><span data-stu-id="893a8-213">The &lt;caching&gt; section must appear within the &lt;system.web&gt; section of a web configuration file.</span></span>

<span data-ttu-id="893a8-214">**列出 6 – web.config 的快取 > 章節**</span><span class="sxs-lookup"><span data-stu-id="893a8-214">**Listing 6 – Caching section for web.config**</span></span>

[!code-xml[Main](improving-performance-with-output-caching-cs/samples/sample6.xml)]

<span data-ttu-id="893a8-215">列出 7 中的控制站會說明如何將 Cache1Hour 設定檔套用至控制器動作以 [OutputCache] 屬性。</span><span class="sxs-lookup"><span data-stu-id="893a8-215">The controller in Listing 7 illustrates how you can apply the Cache1Hour profile to a controller action with the [OutputCache] attribute.</span></span>

<span data-ttu-id="893a8-216">**列出 7 – Controllers\ProfileController.cs**</span><span class="sxs-lookup"><span data-stu-id="893a8-216">**Listing 7 – Controllers\ProfileController.cs**</span></span>

[!code-csharp[Main](improving-performance-with-output-caching-cs/samples/sample7.cs)]

<span data-ttu-id="893a8-217">如果您叫用列出 7 中的控制站所公開的 index 動作將會 （1 小時） 傳回相同的時間。</span><span class="sxs-lookup"><span data-stu-id="893a8-217">If you invoke the Index() action exposed by the controller in Listing 7 then the same time will be returned for 1 hour.</span></span>

## <a name="summary"></a><span data-ttu-id="893a8-218">總結</span><span class="sxs-lookup"><span data-stu-id="893a8-218">Summary</span></span>

<span data-ttu-id="893a8-219">輸出快取可以提供大幅改善效能的 ASP.NET MVC 應用程式的簡單方法。</span><span class="sxs-lookup"><span data-stu-id="893a8-219">Output caching provides you with a very easy method of dramatically improving the performance of your ASP.NET MVC applications.</span></span> <span data-ttu-id="893a8-220">在本教學課程中，您將學會如何使用非同步控制器動作的輸出快取 [OutputCache] 屬性。</span><span class="sxs-lookup"><span data-stu-id="893a8-220">In this tutorial, you learned how to use the [OutputCache] attribute to cache the output of controller actions.</span></span> <span data-ttu-id="893a8-221">您也學會如何修改 [OutputCache] 屬性，例如持續時間和 VaryByParam 屬性來修改內容取得快取的內容。</span><span class="sxs-lookup"><span data-stu-id="893a8-221">You also learned how to modify properties of the [OutputCache] attribute such as the Duration and VaryByParam properties to modify how content gets cached.</span></span> <span data-ttu-id="893a8-222">最後，您學會如何在 web 組態檔中定義快取設定檔。</span><span class="sxs-lookup"><span data-stu-id="893a8-222">Finally, you learned how to define cache profiles in the web configuration file.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="893a8-223">[上一頁](understanding-action-filters-cs.md)
[下一頁](adding-dynamic-content-to-a-cached-page-cs.md)</span><span class="sxs-lookup"><span data-stu-id="893a8-223">[Previous](understanding-action-filters-cs.md)
[Next](adding-dynamic-content-to-a-cached-page-cs.md)</span></span>