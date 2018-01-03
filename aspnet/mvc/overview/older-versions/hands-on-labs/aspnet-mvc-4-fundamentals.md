---
uid: mvc/overview/older-versions/hands-on-labs/aspnet-mvc-4-fundamentals
title: "ASP.NET MVC 4 的基本概念 |Microsoft 文件"
author: rick-anderson
description: "這個實際操作實驗室根據 MVC （模型檢視控制器） Music Store 教學課程的應用程式的介紹，並逐步說明如何使用 ASP.NET MV..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 02/18/2013
ms.topic: article
ms.assetid: b7dba543-73c3-4534-a9a0-ba70fa2c6a8a
ms.technology: dotnet-mvc
ms.prod: .net-framework
msc.legacyurl: /mvc/overview/older-versions/hands-on-labs/aspnet-mvc-4-fundamentals
msc.type: authoredcontent
ms.openlocfilehash: 086084b63cceca1c2d4e0bd4e5b654aaad6637a9
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2017
---
<a name="aspnet-mvc-4-fundamentals"></a><span data-ttu-id="abdb3-103">ASP.NET MVC 4 的基本概念</span><span class="sxs-lookup"><span data-stu-id="abdb3-103">ASP.NET MVC 4 Fundamentals</span></span>
====================
<span data-ttu-id="abdb3-104">由[Web 營小組](https://twitter.com/webcamps)</span><span class="sxs-lookup"><span data-stu-id="abdb3-104">by [Web Camps Team](https://twitter.com/webcamps)</span></span>

> <span data-ttu-id="abdb3-105">這個實際操作實驗室是以 MVC （模型檢視控制器） Music Store 教學課程的應用程式的介紹，並逐步說明如何使用 ASP.NET MVC 和 Visual Studio 為基礎。</span><span class="sxs-lookup"><span data-stu-id="abdb3-105">This Hands-On Lab is based on MVC (Model View Controller) Music Store, a tutorial application that introduces and explains step-by-step how to use ASP.NET MVC and Visual Studio.</span></span> <span data-ttu-id="abdb3-106">在實驗室中，您將學習簡單起見，尚未一起使用這些技術的電源。</span><span class="sxs-lookup"><span data-stu-id="abdb3-106">Throughout the lab you will learn the simplicity, yet power of using these technologies together.</span></span> <span data-ttu-id="abdb3-107">您將使用簡單的應用程式啟動，將建置直到您正常 ASP.NET MVC 4 Web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-107">You will start with a simple application and will build it until you have a fully functional ASP.NET MVC 4 Web Application.</span></span>
> 
> <span data-ttu-id="abdb3-108">這個實驗室搭配 ASP.NET MVC 4。</span><span class="sxs-lookup"><span data-stu-id="abdb3-108">This Lab works with ASP.NET MVC 4.</span></span>
> 
> <span data-ttu-id="abdb3-109">如果您想要瀏覽教學課程的應用程式的 ASP.NET MVC 3 版本，您可以尋找在[MVC Music Store](https://github.com/evilDave/MVC-Music-Store)。</span><span class="sxs-lookup"><span data-stu-id="abdb3-109">If you wish to explore the ASP.NET MVC 3 version of the tutorial application, you can find it in [MVC-Music-Store](https://github.com/evilDave/MVC-Music-Store).</span></span>
> 
> > [!NOTE]
> > <span data-ttu-id="abdb3-110">這個實際操作實驗室假設開發人員體驗中的 Web 開發技術，例如 HTML 和 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="abdb3-110">This Hands-On Lab assumes that the developer has experience in Web development technologies, such as HTML and JavaScript.</span></span>
> 
> 
> <span data-ttu-id="abdb3-111">所有的範例程式碼和程式碼片段會包含在 Web 營訓練套件，可在[https://www.microsoft.com/en-us/download/29843](https://www.microsoft.com/en-us/download/29843)。</span><span class="sxs-lookup"><span data-stu-id="abdb3-111">All sample code and snippets are included in the Web Camps Training Kit, available at [https://www.microsoft.com/en-us/download/29843](https://www.microsoft.com/en-us/download/29843).</span></span>


<a id="The_Music_Store_application"></a>
### <a name="the-music-store-application"></a><span data-ttu-id="abdb3-112">Music Store 應用程式</span><span class="sxs-lookup"><span data-stu-id="abdb3-112">The Music Store application</span></span>

<span data-ttu-id="abdb3-113">將建置這個實驗室整個 Music Store web 應用程式包含三個主要部分： 購物、 簽出，以及系統管理。</span><span class="sxs-lookup"><span data-stu-id="abdb3-113">The Music Store web application that will be built throughout this Lab comprises three main parts: shopping, checkout, and administration.</span></span> <span data-ttu-id="abdb3-114">訪客可以瀏覽相簿的內容類型、 將專輯新增至購物車、 檢閱其選項和最後繼續簽出以登入並完成訂購。</span><span class="sxs-lookup"><span data-stu-id="abdb3-114">Visitors will be able to browse albums by genre, add albums to their cart, review their selection and finally proceed to checkout to login and complete the order.</span></span> <span data-ttu-id="abdb3-115">此外，存放區系統管理員將能夠管理可用的相簿，以及其主要屬性。</span><span class="sxs-lookup"><span data-stu-id="abdb3-115">Additionally, store administrators will be able to manage the available albums as well as their main properties.</span></span>

<span data-ttu-id="abdb3-116">![Music Store 畫面](aspnet-mvc-4-fundamentals/_static/image1.png "Music Store 螢幕")</span><span class="sxs-lookup"><span data-stu-id="abdb3-116">![Music Store screens](aspnet-mvc-4-fundamentals/_static/image1.png "Music Store screens")</span></span>

<span data-ttu-id="abdb3-117">*Music Store 畫面*</span><span class="sxs-lookup"><span data-stu-id="abdb3-117">*Music Store screens*</span></span>

<a id="ASPNET_MVC_4_Essentials"></a>
### <a name="aspnet-mvc-4-essentials"></a><span data-ttu-id="abdb3-118">ASP.NET MVC 4 Essentials</span><span class="sxs-lookup"><span data-stu-id="abdb3-118">ASP.NET MVC 4 Essentials</span></span>

<span data-ttu-id="abdb3-119">Music Store 應用程式將會使用建置**模型檢視控制器 (MVC)**，分隔成三個主要元件的應用程式的架構模式：</span><span class="sxs-lookup"><span data-stu-id="abdb3-119">Music Store application will be built using **Model View Controller (MVC)**, an architectural pattern that separates an application into three main components:</span></span>

- <span data-ttu-id="abdb3-120">**模型**： 模型物件屬於實作網域邏輯之應用程式一部分。</span><span class="sxs-lookup"><span data-stu-id="abdb3-120">**Models**: Model objects are the parts of the application that implement the domain logic.</span></span> <span data-ttu-id="abdb3-121">通常，模型物件也擷取並儲存在資料庫中的模型狀態。</span><span class="sxs-lookup"><span data-stu-id="abdb3-121">Often, model objects also retrieve and store model state in a database.</span></span>
- <span data-ttu-id="abdb3-122">**檢視：**檢視會顯示應用程式的使用者介面 (UI) 的元件。</span><span class="sxs-lookup"><span data-stu-id="abdb3-122">**Views:** Views are the components that display the application's user interface (UI).</span></span> <span data-ttu-id="abdb3-123">一般而言，此 UI 是從模型資料的方式建立。</span><span class="sxs-lookup"><span data-stu-id="abdb3-123">Typically, this UI is created from the model data.</span></span> <span data-ttu-id="abdb3-124">範例會顯示文字方塊和下拉式清單的專輯物件的目前狀態為基礎的相簿編輯檢視。</span><span class="sxs-lookup"><span data-stu-id="abdb3-124">An example would be the edit view of Albums that displays text boxes and a drop-down list based on the current state of an Album object.</span></span>
- <span data-ttu-id="abdb3-125">**控制站：**控制站是可處理使用者互動、 使用模型，以及最後選取的檢視呈現 UI 元件。</span><span class="sxs-lookup"><span data-stu-id="abdb3-125">**Controllers:** Controllers are the components that handle user interaction, manipulate the model, and ultimately select a view to render the UI.</span></span> <span data-ttu-id="abdb3-126">MVC 應用程式中，檢視只能顯示資訊。控制器會處理和回應使用者輸入和互動。</span><span class="sxs-lookup"><span data-stu-id="abdb3-126">In an MVC application, the view only displays information; the controller handles and responds to user input and interaction.</span></span>

<span data-ttu-id="abdb3-127">MVC 模式可協助您建立個別的不同層面的應用程式 （輸入的邏輯、 商務邏輯和 UI 邏輯），同時提供這些項目之間的鬆散偶合的應用程式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-127">The MVC pattern helps you to create applications that separate the different aspects of the application (input logic, business logic, and UI logic), while providing a loose coupling between these elements.</span></span> <span data-ttu-id="abdb3-128">此隔離有助於您管理複雜度，當您建置應用程式，因為它可讓您將焦點放在上一次實作的其中一個層面。</span><span class="sxs-lookup"><span data-stu-id="abdb3-128">This separation helps you manage complexity when you build an application, as it allows you to focus on one aspect of the implementation at a time.</span></span> <span data-ttu-id="abdb3-129">此外，MVC 模式讓您輕鬆地測試應用程式，也鼓勵測試為導向的開發 (TDD) 用於建立應用程式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-129">In addition, the MVC pattern makes it easy to test applications, also encouraging the use of test-driven development (TDD) for creating applications.</span></span>

<span data-ttu-id="abdb3-130">**ASP.NET MVC** framework 提供用於建立 ASP.NET MVC 為基礎的 Web 應用程式的 ASP.NET Web Form 模式的替代方案。</span><span class="sxs-lookup"><span data-stu-id="abdb3-130">The **ASP.NET MVC** framework provides an alternative to the ASP.NET Web Forms pattern for creating ASP.NET MVC-based Web applications.</span></span> <span data-ttu-id="abdb3-131">**ASP.NET MVC**架構是一種輕量型、 可高度測試的呈現架構，（如同搭配 Web 表單架構應用程式） 整合了現有 ASP.NET 功能，例如主版頁面和成員資格為基礎驗證讓您取得核心.NET framework 的所有功能。</span><span class="sxs-lookup"><span data-stu-id="abdb3-131">The **ASP.NET MVC** framework is a lightweight, highly testable presentation framework that (as with Web-forms-based applications) is integrated with existing ASP.NET features, such as master pages and membership-based authentication so you get all the power of the core .NET framework.</span></span> <span data-ttu-id="abdb3-132">這非常有用，如果您已經熟悉 ASP.NET Web Form 因為您已經使用的所有程式庫也可使用 ASP.NET MVC 4。</span><span class="sxs-lookup"><span data-stu-id="abdb3-132">This is useful if you are already familiar with ASP.NET Web Forms because all the libraries that you already use are available in ASP.NET MVC 4 as well.</span></span>

<span data-ttu-id="abdb3-133">此外，在 MVC 應用程式的三個主要元件之間的鬆散連接也有助於提升平行開發。</span><span class="sxs-lookup"><span data-stu-id="abdb3-133">In addition, the loose coupling between the three main components of an MVC application also promotes parallel development.</span></span> <span data-ttu-id="abdb3-134">比方說，一個開發人員可以使用檢視、 第二個開發人員可以在控制器邏輯，而且第三個開發人員可以專注於商務邏輯模型中。</span><span class="sxs-lookup"><span data-stu-id="abdb3-134">For instance, one developer can work on the view, a second developer can work on the controller logic, and a third developer can focus on the business logic in the model.</span></span>

<a id="Objectives"></a>

<a id="Objectives"></a>
### <a name="objectives"></a><span data-ttu-id="abdb3-135">目標</span><span class="sxs-lookup"><span data-stu-id="abdb3-135">Objectives</span></span>

<span data-ttu-id="abdb3-136">在這個實際操作實驗室中，您將學會如何：</span><span class="sxs-lookup"><span data-stu-id="abdb3-136">In this Hands-On Lab, you will learn how to:</span></span>

- <span data-ttu-id="abdb3-137">根據音樂市集應用程式教學課程從頭開始建立 ASP.NET MVC 應用程式</span><span class="sxs-lookup"><span data-stu-id="abdb3-137">Create an ASP.NET MVC application from scratch based on the Music Store Application tutorial</span></span>
- <span data-ttu-id="abdb3-138">新增控制站來處理至站台，並瀏覽其主要功能的首頁的 Url</span><span class="sxs-lookup"><span data-stu-id="abdb3-138">Add Controllers to handle URLs to the Home page of the site and for browsing its main functionality</span></span>
- <span data-ttu-id="abdb3-139">加入檢視，以自訂其樣式以及顯示的內容</span><span class="sxs-lookup"><span data-stu-id="abdb3-139">Add a View to customize the content displayed along with its style</span></span>
- <span data-ttu-id="abdb3-140">新增模型類別來管理資料和網域邏輯</span><span class="sxs-lookup"><span data-stu-id="abdb3-140">Add Model classes to contain and manage data and domain logic</span></span>
- <span data-ttu-id="abdb3-141">使用檢視模型 」 模式的控制器動作的資訊傳遞至檢視範本</span><span class="sxs-lookup"><span data-stu-id="abdb3-141">Use View Model pattern to pass information from controller actions to the view templates</span></span>
- <span data-ttu-id="abdb3-142">瀏覽網際網路應用程式的 ASP.NET MVC 4 新範本</span><span class="sxs-lookup"><span data-stu-id="abdb3-142">Explore the ASP.NET MVC 4 new template for internet applications</span></span>

<a id="Prerequisites"></a>

<a id="Prerequisites"></a>
### <a name="prerequisites"></a><span data-ttu-id="abdb3-143">必要條件</span><span class="sxs-lookup"><span data-stu-id="abdb3-143">Prerequisites</span></span>

<span data-ttu-id="abdb3-144">您必須具備下列項目才能完成本實驗室：</span><span class="sxs-lookup"><span data-stu-id="abdb3-144">You must have the following items to complete this lab:</span></span>

- <span data-ttu-id="abdb3-145">[Visual Studio 2012 Express for Web](https://www.microsoft.com/visualstudio/eng/products/visual-studio-express-for-web) (讀取[附錄 A](#AppendixA)如需有關如何安裝指示)</span><span class="sxs-lookup"><span data-stu-id="abdb3-145">[Visual Studio 2012 Express for Web](https://www.microsoft.com/visualstudio/eng/products/visual-studio-express-for-web) (read [Appendix A](#AppendixA) for instructions on how to install it)</span></span>

<a id="Setup"></a>

<a id="Setup"></a>
### <a name="setup"></a><span data-ttu-id="abdb3-146">安裝程式</span><span class="sxs-lookup"><span data-stu-id="abdb3-146">Setup</span></span>

<span data-ttu-id="abdb3-147">**安裝程式碼片段**</span><span class="sxs-lookup"><span data-stu-id="abdb3-147">**Installing Code Snippets**</span></span>

<span data-ttu-id="abdb3-148">為了方便起見，大部分您將沿著這個實驗室管理的程式碼可做為 Visual Studio 程式碼片段。</span><span class="sxs-lookup"><span data-stu-id="abdb3-148">For convenience, much of the code you will be managing along this lab is available as Visual Studio code snippets.</span></span> <span data-ttu-id="abdb3-149">若要安裝執行的程式碼片段**.\Source\Setup\CodeSnippets.vsi**檔案。</span><span class="sxs-lookup"><span data-stu-id="abdb3-149">To install the code snippets run **.\Source\Setup\CodeSnippets.vsi** file.</span></span>

<span data-ttu-id="abdb3-150">如果您不熟悉 Visual Studio 程式碼片段，而且想来了解如何使用它們，您可以從這份文件參考附錄&quot;[附錄 c： 使用程式碼片段](#AppendixC)&quot;。</span><span class="sxs-lookup"><span data-stu-id="abdb3-150">If you are not familiar with the Visual Studio Code Snippets, and want to learn how to use them, you can refer to the appendix from this document &quot;[Appendix C: Using Code Snippets](#AppendixC)&quot;.</span></span>

<a id="Exercises"></a>

<a id="Exercises"></a>
## <a name="exercises"></a><span data-ttu-id="abdb3-151">練習</span><span class="sxs-lookup"><span data-stu-id="abdb3-151">Exercises</span></span>

<span data-ttu-id="abdb3-152">這個實際操作實驗室是由下列練習所組成：</span><span class="sxs-lookup"><span data-stu-id="abdb3-152">This Hands-On Lab is comprised by the following exercises:</span></span>

1. [<span data-ttu-id="abdb3-153">練習 1： 建立 MusicStore ASP.NET MVC Web 應用程式專案</span><span class="sxs-lookup"><span data-stu-id="abdb3-153">Exercise 1: Creating MusicStore ASP.NET MVC Web Application Project</span></span>](#Exercise1)
2. [<span data-ttu-id="abdb3-154">練習 2： 建立控制站</span><span class="sxs-lookup"><span data-stu-id="abdb3-154">Exercise 2: Creating a Controller</span></span>](#Exercise2)
3. [<span data-ttu-id="abdb3-155">練習 3： 將參數傳遞至控制器</span><span class="sxs-lookup"><span data-stu-id="abdb3-155">Exercise 3: Passing parameters to a Controller</span></span>](#Exercise3)
4. [<span data-ttu-id="abdb3-156">練習 4： 建立檢視</span><span class="sxs-lookup"><span data-stu-id="abdb3-156">Exercise 4: Creating a View</span></span>](#Exercise4)
5. [<span data-ttu-id="abdb3-157">練習 5： 建立檢視模型</span><span class="sxs-lookup"><span data-stu-id="abdb3-157">Exercise 5: Creating a View Model</span></span>](#Exercise5)
6. [<span data-ttu-id="abdb3-158">練習 6： 在檢視中使用參數</span><span class="sxs-lookup"><span data-stu-id="abdb3-158">Exercise 6: Using parameters in View</span></span>](#Exercise6)
7. [<span data-ttu-id="abdb3-159">練習 7： 一圈住 ASP.NET MVC 4 的新範本</span><span class="sxs-lookup"><span data-stu-id="abdb3-159">Exercise 7: A lap around ASP.NET MVC 4 New Template</span></span>](#Exercise7)

> [!NOTE]
> <span data-ttu-id="abdb3-160">每個練習會伴隨著**結束**包含所產生的解決方案完成練習之後，您應該取得資料夾。</span><span class="sxs-lookup"><span data-stu-id="abdb3-160">Each exercise is accompanied by an **End** folder containing the resulting solution you should obtain after completing the exercises.</span></span> <span data-ttu-id="abdb3-161">如果您需要其他協助使用的所有練習，您可以使用這個方案做為指南。</span><span class="sxs-lookup"><span data-stu-id="abdb3-161">You can use this solution as a guide if you need additional help working through the exercises.</span></span>


<span data-ttu-id="abdb3-162">完成本實驗室估計時間： **60 分鐘**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-162">Estimated time to complete this lab: **60 minutes**.</span></span>

<a id="Exercise1"></a>

<a id="Exercise_1_Creating_MusicStore_ASPNET_MVC_Web_Application_Project"></a>
### <a name="exercise-1-creating-musicstore-aspnet-mvc-web-application-project"></a><span data-ttu-id="abdb3-163">練習 1： 建立 MusicStore ASP.NET MVC Web 應用程式專案</span><span class="sxs-lookup"><span data-stu-id="abdb3-163">Exercise 1: Creating MusicStore ASP.NET MVC Web Application Project</span></span>

<span data-ttu-id="abdb3-164">在此練習中，您將學習如何建立 ASP.NET MVC 應用程式在 Visual Studio 2012 Express 網站以及其主要資料夾組織。</span><span class="sxs-lookup"><span data-stu-id="abdb3-164">In this exercise, you will learn how to create an ASP.NET MVC application in Visual Studio 2012 Express for Web as well as its main folder organization.</span></span> <span data-ttu-id="abdb3-165">此外，您將學習如何加入新的控制器，並讓它在應用程式的首頁上顯示簡單的字串。</span><span class="sxs-lookup"><span data-stu-id="abdb3-165">Additionally, you will learn how to add a new Controller and make it display a simple string in the application's home page.</span></span>

<a id="Ex1Task1"></a>

<a id="Task_1_-_Creating_the_ASPNET_MVC_Web_Application_Project"></a>
#### <a name="task-1---creating-the-aspnet-mvc-web-application-project"></a><span data-ttu-id="abdb3-166">工作 1-建立 ASP.NET MVC Web 應用程式專案</span><span class="sxs-lookup"><span data-stu-id="abdb3-166">Task 1 - Creating the ASP.NET MVC Web Application Project</span></span>

1. <span data-ttu-id="abdb3-167">在這項工作，您將建立空白 ASP.NET MVC 應用程式專案使用 MVC 的 Visual Studio 範本。</span><span class="sxs-lookup"><span data-stu-id="abdb3-167">In this task, you will create an empty ASP.NET MVC application project using the MVC Visual Studio template.</span></span> <span data-ttu-id="abdb3-168">啟動**VS Express for Web**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-168">Start **VS Express for Web**.</span></span>
2. <span data-ttu-id="abdb3-169">按一下 [檔案] 功能表上的 [新增專案]。</span><span class="sxs-lookup"><span data-stu-id="abdb3-169">On the **File** menu, click **New Project**.</span></span>
3. <span data-ttu-id="abdb3-170">在**新專案**對話方塊中，選取**ASP.NET MVC 4 Web 應用程式**專案類型，位於**Visual C#** **Web**範本清單。</span><span class="sxs-lookup"><span data-stu-id="abdb3-170">In the **New Project** dialog box select the **ASP.NET MVC 4 Web Application** project type, located under **Visual C#,** **Web** template list.</span></span>
4. <span data-ttu-id="abdb3-171">變更**名稱**至*MvcMusicStore*。</span><span class="sxs-lookup"><span data-stu-id="abdb3-171">Change the **Name** to *MvcMusicStore*.</span></span>
5. <span data-ttu-id="abdb3-172">設定內的新方案的位置**開始**資料夾，在此練習中的來源資料夾中，例如**[您-HOL-PATH] \Source\Ex01-CreatingMusicStoreProject\Begin**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-172">Set the location of the solution inside a new **Begin** folder in this Exercise's Source folder, for example **[YOUR-HOL-PATH]\Source\Ex01-CreatingMusicStoreProject\Begin**.</span></span> <span data-ttu-id="abdb3-173">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="abdb3-173">Click **OK**.</span></span>

    <span data-ttu-id="abdb3-174">![建立新專案 對話方塊](aspnet-mvc-4-fundamentals/_static/image2.png "建立新專案 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="abdb3-174">![Create New Project Dialog Box](aspnet-mvc-4-fundamentals/_static/image2.png "Create New Project Dialog Box")</span></span>

    <span data-ttu-id="abdb3-175">*建立新專案 對話方塊*</span><span class="sxs-lookup"><span data-stu-id="abdb3-175">*Create New Project Dialog Box*</span></span>
6. <span data-ttu-id="abdb3-176">在**新增 ASP.NET MVC 4 專案**對話方塊中，選取**基本**範本並確定**檢視引擎**選取**Razor**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-176">In the **New ASP.NET MVC 4 Project** dialog box select the **Basic** template and make sure that the **View engine** selected is **Razor**.</span></span> <span data-ttu-id="abdb3-177">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="abdb3-177">Click **OK**.</span></span>

    <span data-ttu-id="abdb3-178">![新 ASP.NET MVC 4 專案 對話方塊](aspnet-mvc-4-fundamentals/_static/image3.png "新 ASP.NET MVC 4 專案 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="abdb3-178">![New ASP.NET MVC 4 Project Dialog Box](aspnet-mvc-4-fundamentals/_static/image3.png "New ASP.NET MVC 4 Project Dialog Box")</span></span>

    <span data-ttu-id="abdb3-179">*新增 ASP.NET MVC 4 專案對話方塊*</span><span class="sxs-lookup"><span data-stu-id="abdb3-179">*New ASP.NET MVC 4 Project Dialog Box*</span></span>

<a id="Ex1Task2"></a>

<a id="Task_2_-_Exploring_the_Solution_Structure"></a>
#### <a name="task-2---exploring-the-solution-structure"></a><span data-ttu-id="abdb3-180">工作 2-瀏覽方案結構</span><span class="sxs-lookup"><span data-stu-id="abdb3-180">Task 2 - Exploring the Solution Structure</span></span>

<span data-ttu-id="abdb3-181">ASP.NET MVC 架構包括 Visual Studio 專案範本，可協助您建立 Web 應用程式支援 MVC 模式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-181">The ASP.NET MVC framework includes a Visual Studio project template that helps you create Web applications supporting the MVC pattern.</span></span> <span data-ttu-id="abdb3-182">此範本建立新的 ASP.NET MVC Web 應用程式具有必要的資料夾、 項目範本和組態檔項目。</span><span class="sxs-lookup"><span data-stu-id="abdb3-182">This template creates a new ASP.NET MVC Web application with the required folders, item templates, and configuration-file entries.</span></span>

<span data-ttu-id="abdb3-183">在這項工作，您將檢查方案結構，以了解所涉及的項目和其關聯性。</span><span class="sxs-lookup"><span data-stu-id="abdb3-183">In this task, you will examine the solution structure to understand the elements that are involved and their relationships.</span></span> <span data-ttu-id="abdb3-184">下列資料夾會包含在 ASP.NET MVC 應用程式，因為預設的 ASP.NET MVC 架構會使用&quot;慣例，透過組態&quot;方法，並進行一些預設假設根據命名資料夾慣例。</span><span class="sxs-lookup"><span data-stu-id="abdb3-184">The following folders are included in all the ASP.NET MVC application because the ASP.NET MVC framework by default uses a &quot;convention over configuration&quot; approach, and makes some default assumptions based on folder naming conventions.</span></span>

1. <span data-ttu-id="abdb3-185">一旦建立專案之後，請檢閱在右邊的 [方案總管] 中所建立的資料夾結構：</span><span class="sxs-lookup"><span data-stu-id="abdb3-185">Once the project is created, review the folder structure that has been created in the Solution Explorer on the right side:</span></span>

    <span data-ttu-id="abdb3-186">![在 [方案總管] 中的 ASP.NET MVC 資料夾結構](aspnet-mvc-4-fundamentals/_static/image4.png "方案總管 中的 ASP.NET MVC 資料夾結構")</span><span class="sxs-lookup"><span data-stu-id="abdb3-186">![ASP.NET MVC Folder structure in Solution Explorer](aspnet-mvc-4-fundamentals/_static/image4.png "ASP.NET MVC Folder structure in Solution Explorer")</span></span>

    <span data-ttu-id="abdb3-187">*在 [方案總管] 中的 ASP.NET MVC 資料夾結構*</span><span class="sxs-lookup"><span data-stu-id="abdb3-187">*ASP.NET MVC Folder structure in Solution Explorer*</span></span>

    1. <span data-ttu-id="abdb3-188">**控制站**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-188">**Controllers**.</span></span> <span data-ttu-id="abdb3-189">這個資料夾將包含控制器類別。</span><span class="sxs-lookup"><span data-stu-id="abdb3-189">This folder will contain the controller classes.</span></span> <span data-ttu-id="abdb3-190">基礎的 MVC 應用程式中，控制站負責處理使用者互動、 管理模型，以及最後選擇要呈現 UI 的檢視。</span><span class="sxs-lookup"><span data-stu-id="abdb3-190">In an MVC based application, controllers are responsible for handling end user interaction, manipulating the model, and ultimately choosing a view to render the UI.</span></span>

        > [!NOTE]
        > <span data-ttu-id="abdb3-191">MVC framework 需要以結尾的所有控制器的名稱&quot;控制器&quot;-例如 HomeController、 LoginController 或 ProductController。</span><span class="sxs-lookup"><span data-stu-id="abdb3-191">The MVC framework requires the names of all controllers to end with &quot;Controller&quot;-for example, HomeController, LoginController, or ProductController.</span></span>
    2. <span data-ttu-id="abdb3-192">**模型**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-192">**Models**.</span></span> <span data-ttu-id="abdb3-193">表示 MVC Web 應用程式的應用程式模型的類別提供此資料夾。</span><span class="sxs-lookup"><span data-stu-id="abdb3-193">This folder is provided for classes that represent the application model for the MVC Web application.</span></span> <span data-ttu-id="abdb3-194">這通常會包含定義物件和的邏輯與資料存放區互動的程式碼。</span><span class="sxs-lookup"><span data-stu-id="abdb3-194">This usually includes code that defines objects and the logic for interacting with the data store.</span></span> <span data-ttu-id="abdb3-195">通常，實際的模型物件會在不同的類別庫中。</span><span class="sxs-lookup"><span data-stu-id="abdb3-195">Typically, the actual model objects will be in separate class libraries.</span></span> <span data-ttu-id="abdb3-196">不過，當您建立新的應用程式，您可能會包含類別，並移至不同的類別庫，在稍後在開發週期中。</span><span class="sxs-lookup"><span data-stu-id="abdb3-196">However, when you create a new application, you might include classes and then move them into separate class libraries at a later point in the development cycle.</span></span>
    3. <span data-ttu-id="abdb3-197">**檢視**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-197">**Views**.</span></span> <span data-ttu-id="abdb3-198">此資料夾是檢視，負責顯示應用程式的使用者介面元件的建議的位置。</span><span class="sxs-lookup"><span data-stu-id="abdb3-198">This folder is the recommended location for views, the components responsible for displaying the application's user interface.</span></span> <span data-ttu-id="abdb3-199">檢視使用.aspx、.ascx、.cshtml 和.master 檔案中，除了與呈現檢視相關的任何其他檔案。</span><span class="sxs-lookup"><span data-stu-id="abdb3-199">Views use .aspx, .ascx, .cshtml and .master files, in addition to any other files that are related to rendering views.</span></span> <span data-ttu-id="abdb3-200">檢視資料夾包含的每一個控制器。此資料夾以控制器名稱的前置詞命名。</span><span class="sxs-lookup"><span data-stu-id="abdb3-200">Views folder contains a folder for each controller; the folder is named with the controller-name prefix.</span></span> <span data-ttu-id="abdb3-201">例如，如果您有名稱為控制器**HomeController**，[檢視] 資料夾會包含名為 Home 的資料夾。</span><span class="sxs-lookup"><span data-stu-id="abdb3-201">For example, if you have a controller named **HomeController**, the Views folder will contain a folder named Home.</span></span> <span data-ttu-id="abdb3-202">根據預設，當 ASP.NET MVC 架構載入檢視時，它會尋找具有 Views\controllerName 資料夾中之要求的檢視名稱的.aspx 檔案 (**檢視 [ControllerName] [動作].aspx**) 或 (**檢視 [ControllerName][動作].cshtml**) Razor 檢視的。</span><span class="sxs-lookup"><span data-stu-id="abdb3-202">By default, when the ASP.NET MVC framework loads a view, it looks for an .aspx file with the requested view name in the Views\controllerName folder (**Views[ControllerName][Action].aspx**) or (**Views[ControllerName][Action].cshtml**) for Razor Views.</span></span>

    > [!NOTE]
    > <span data-ttu-id="abdb3-203">除了前面列出的資料夾，MVC Web 應用程式會使用**Global.asax**檔案來設定全域 URL 路由預設值，並使用**Web.config**檔案來設定應用程式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-203">In addition to the folders listed previously, an MVC Web application uses the **Global.asax** file to set global URL routing defaults, and it uses the **Web.config** file to configure the application.</span></span>

<a id="Ex1Task3"></a>

<a id="Task_3_-_Adding_a_HomeController"></a>
#### <a name="task-3---adding-a-homecontroller"></a><span data-ttu-id="abdb3-204">工作 3-加入 HomeController</span><span class="sxs-lookup"><span data-stu-id="abdb3-204">Task 3 - Adding a HomeController</span></span>

<span data-ttu-id="abdb3-205">在不使用 MVC 架構的 ASP.NET 應用程式，使用者互動會圍繞網頁以及引發和處理事件從那些頁面加以組織。</span><span class="sxs-lookup"><span data-stu-id="abdb3-205">In ASP.NET applications that do not use the MVC framework, user interaction is organized around pages, and around raising and handling events from those pages.</span></span> <span data-ttu-id="abdb3-206">相反地，ASP.NET MVC 應用程式的使用者互動會圍繞控制器和動作方法加以組織。</span><span class="sxs-lookup"><span data-stu-id="abdb3-206">In contrast, user interaction with ASP.NET MVC applications is organized around controllers and their action methods.</span></span>

<span data-ttu-id="abdb3-207">相反地，ASP.NET MVC 架構會將 Url 對應至稱為 「 控制站的類別。</span><span class="sxs-lookup"><span data-stu-id="abdb3-207">On the other hand, ASP.NET MVC framework maps URLs to classes that are referred to as controllers.</span></span> <span data-ttu-id="abdb3-208">控制站處理傳入的要求、 處理使用者輸入和互動、 執行適當的應用程式邏輯並決定要傳送回用戶端的回應 （顯示 HTML、 下載檔案、 重新導向至不同的 URL，依此類推）。</span><span class="sxs-lookup"><span data-stu-id="abdb3-208">Controllers process incoming requests, handle user input and interactions, execute appropriate application logic and determine the response to send back to the client (display HTML, download a file, redirect to a different URL, etc.).</span></span> <span data-ttu-id="abdb3-209">在顯示 HTML，控制器類別通常會呼叫不同的檢視元件來產生要求的 HTML 標記。</span><span class="sxs-lookup"><span data-stu-id="abdb3-209">In the case of displaying HTML, a controller class typically calls a separate view component to generate the HTML markup for the request.</span></span> <span data-ttu-id="abdb3-210">MVC 應用程式中，檢視只能顯示資訊。控制器會處理和回應使用者輸入和互動。</span><span class="sxs-lookup"><span data-stu-id="abdb3-210">In an MVC application, the view only displays information; the controller handles and responds to user input and interaction.</span></span>

<span data-ttu-id="abdb3-211">在這項工作，您將加入控制器類別處理 Music Store 網站的首頁 Url。</span><span class="sxs-lookup"><span data-stu-id="abdb3-211">In this task, you will add a Controller class that will handle URLs to the Home page of the Music Store site.</span></span>

1. <span data-ttu-id="abdb3-212">以滑鼠右鍵按一下**控制器**資料夾在方案總管中，選取**新增**然後**控制器**命令：</span><span class="sxs-lookup"><span data-stu-id="abdb3-212">Right-click **Controllers** folder within the Solution Explorer, select **Add** and then **Controller** command:</span></span>

    <span data-ttu-id="abdb3-213">![加入控制器命令](aspnet-mvc-4-fundamentals/_static/image5.png "新增控制器命令")</span><span class="sxs-lookup"><span data-stu-id="abdb3-213">![Add a Controller Command](aspnet-mvc-4-fundamentals/_static/image5.png "Add a Controller Command")</span></span>

    <span data-ttu-id="abdb3-214">*加入控制器命令*</span><span class="sxs-lookup"><span data-stu-id="abdb3-214">*Add Controller Command*</span></span>
2. <span data-ttu-id="abdb3-215">**加入控制器**對話方塊隨即出現。</span><span class="sxs-lookup"><span data-stu-id="abdb3-215">The **Add Controller** dialog appears.</span></span> <span data-ttu-id="abdb3-216">控制器*HomeController*按**新增**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-216">Name the controller *HomeController* and press **Add**.</span></span>

    <span data-ttu-id="abdb3-217">![加入控制器 對話方塊](aspnet-mvc-4-fundamentals/_static/image6.png "加入控制器 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="abdb3-217">![Add Controller Dialog](aspnet-mvc-4-fundamentals/_static/image6.png "Add Controller Dialog")</span></span>

    <span data-ttu-id="abdb3-218">*加入控制器 對話方塊*</span><span class="sxs-lookup"><span data-stu-id="abdb3-218">*Add Controller Dialog*</span></span>
3. <span data-ttu-id="abdb3-219">檔案**HomeController.cs**中建立**控制器**資料夾。</span><span class="sxs-lookup"><span data-stu-id="abdb3-219">The file **HomeController.cs** is created in the **Controllers** folder.</span></span> <span data-ttu-id="abdb3-220">若**HomeController**其索引的動作傳回的字串，取代**索引**方法取代下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="abdb3-220">In order to have the **HomeController** return a string on its Index action, replace the **Index** method with the following code:</span></span>

    <span data-ttu-id="abdb3-221">(程式碼片段- *ASP.NET MVC 4 Ex1 HomeController 索引基本概念*)</span><span class="sxs-lookup"><span data-stu-id="abdb3-221">(Code Snippet - *ASP.NET MVC 4 Fundamentals - Ex1 HomeController Index*)</span></span>


    [!code-csharp[Main](aspnet-mvc-4-fundamentals/samples/sample1.cs)]

<a id="Ex1Task4"></a>

<a id="Task_4_-_Running_the_Application"></a>
#### <a name="task-4---running-the-application"></a><span data-ttu-id="abdb3-222">工作 4-執行應用程式</span><span class="sxs-lookup"><span data-stu-id="abdb3-222">Task 4 - Running the Application</span></span>

<span data-ttu-id="abdb3-223">在這項工作，您將會嘗試在 web 瀏覽器應用程式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-223">In this task, you will try out the Application in a web browser.</span></span>

1. <span data-ttu-id="abdb3-224">按**F5**執行應用程式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-224">Press **F5** to run the Application.</span></span> <span data-ttu-id="abdb3-225">編譯專案之後，本機 IIS 網頁伺服器會啟動。</span><span class="sxs-lookup"><span data-stu-id="abdb3-225">The project is compiled and the local IIS Web Server starts.</span></span> <span data-ttu-id="abdb3-226">本機 IIS Web 伺服器會自動開啟網頁瀏覽器指向 Web 伺服器的 URL。</span><span class="sxs-lookup"><span data-stu-id="abdb3-226">The local IIS Web Server will automatically open a web browser pointing to the URL of the Web server.</span></span>

    <span data-ttu-id="abdb3-227">![在網頁瀏覽器中執行的應用程式](aspnet-mvc-4-fundamentals/_static/image7.png "web 瀏覽器中執行的應用程式")</span><span class="sxs-lookup"><span data-stu-id="abdb3-227">![Application running in a web browser](aspnet-mvc-4-fundamentals/_static/image7.png "Application running in a web browser")</span></span>

    <span data-ttu-id="abdb3-228">*在網頁瀏覽器中執行的應用程式*</span><span class="sxs-lookup"><span data-stu-id="abdb3-228">*Application running in a web browser*</span></span>

    > [!NOTE]
    > <span data-ttu-id="abdb3-229">本機 IIS Web 伺服器會執行網站上的隨機可用連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="abdb3-229">The local IIS Web Server will run the website on a random free port number.</span></span> <span data-ttu-id="abdb3-230">在上圖中，在執行站台`http://localhost:50103/`，因此它正在使用連接埠 50103。</span><span class="sxs-lookup"><span data-stu-id="abdb3-230">In the figure above, the site is running at `http://localhost:50103/`, so it's using port 50103.</span></span> <span data-ttu-id="abdb3-231">連接埠號碼可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="abdb3-231">Your port number may vary.</span></span>
2. <span data-ttu-id="abdb3-232">關閉瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="abdb3-232">Close the browser.</span></span>

<a id="Exercise2"></a>

<a id="Exercise_2_Creating_a_Controller"></a>
### <a name="exercise-2-creating-a-controller"></a><span data-ttu-id="abdb3-233">練習 2： 建立控制站</span><span class="sxs-lookup"><span data-stu-id="abdb3-233">Exercise 2: Creating a Controller</span></span>

<span data-ttu-id="abdb3-234">在此練習中，您將學習如何更新控制器以實作簡單的 Music Store 應用程式的功能。</span><span class="sxs-lookup"><span data-stu-id="abdb3-234">In this exercise, you will learn how to update the controller to implement simple functionality of the Music Store application.</span></span> <span data-ttu-id="abdb3-235">該控制器會定義處理每個下列的特定要求的動作方法：</span><span class="sxs-lookup"><span data-stu-id="abdb3-235">That controller will define action methods to handle each of the following specific requests:</span></span>

- <span data-ttu-id="abdb3-236">在 Music Store 中的音樂內容類型清單頁面</span><span class="sxs-lookup"><span data-stu-id="abdb3-236">A listing page of the music genres in the Music Store</span></span>
- <span data-ttu-id="abdb3-237">瀏覽 頁面會列出所有音樂專輯的特定內容類型</span><span class="sxs-lookup"><span data-stu-id="abdb3-237">A browse page that lists all of the music albums for a particular genre</span></span>
- <span data-ttu-id="abdb3-238">顯示有關特定音樂專輯資訊詳細資料頁面</span><span class="sxs-lookup"><span data-stu-id="abdb3-238">A details page that shows information about a specific music album</span></span>

<span data-ttu-id="abdb3-239">針對此練習的範圍，這些動作只會傳回字串到目前為止。</span><span class="sxs-lookup"><span data-stu-id="abdb3-239">For the scope of this exercise, those actions will simply return a string by now.</span></span>

<a id="Ex2Task1"></a>

<a id="Task_1_-_Adding_a_New_StoreController_Class"></a>
#### <a name="task-1---adding-a-new-storecontroller-class"></a><span data-ttu-id="abdb3-240">工作 1-加入新的 StoreController 類別</span><span class="sxs-lookup"><span data-stu-id="abdb3-240">Task 1 - Adding a New StoreController Class</span></span>

<span data-ttu-id="abdb3-241">在這項工作，您將加入新的控制站。</span><span class="sxs-lookup"><span data-stu-id="abdb3-241">In this task, you will add a new Controller.</span></span>

1. <span data-ttu-id="abdb3-242">如果尚未開啟，啟動**VS 2012 Web Express**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-242">If not already open, start **VS Express for Web 2012**.</span></span>
2. <span data-ttu-id="abdb3-243">在**檔案**功能表上，選擇**開啟專案**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-243">In the **File** menu, choose **Open Project**.</span></span> <span data-ttu-id="abdb3-244">在 [開啟專案] 對話方塊中，瀏覽至**Source\Ex02 CreatingAController\Begin**，選取**Begin.sln**按一下**開啟**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-244">In the Open Project dialog, browse to **Source\Ex02-CreatingAController\Begin**, select **Begin.sln** and click **Open**.</span></span> <span data-ttu-id="abdb3-245">或者，您可以繼續使用此方案完成上一個練習之後取得。</span><span class="sxs-lookup"><span data-stu-id="abdb3-245">Alternatively, you may continue with the solution that you obtained after completing the previous exercise.</span></span>

    1. <span data-ttu-id="abdb3-246">如果您開啟提供**開始**方案，您必須下載某些遺漏的 NuGet 套件才能繼續。</span><span class="sxs-lookup"><span data-stu-id="abdb3-246">If you opened the provided **Begin** solution, you will need to download some missing NuGet packages before continue.</span></span> <span data-ttu-id="abdb3-247">若要這樣做，請按一下**專案**功能表，然後選取**管理 NuGet 封裝**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-247">To do this, click the **Project** menu and select **Manage NuGet Packages**.</span></span>
    2. <span data-ttu-id="abdb3-248">在**管理 NuGet 封裝**] 對話方塊中，按一下 [**還原**才能下載遺漏的封裝。</span><span class="sxs-lookup"><span data-stu-id="abdb3-248">In the **Manage NuGet Packages** dialog, click **Restore** in order to download missing packages.</span></span>
    3. <span data-ttu-id="abdb3-249">最後，按一下 建置方案**建置** | **建置方案**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-249">Finally, build the solution by clicking **Build** | **Build Solution**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="abdb3-250">使用 NuGet 的優點之一是您不需要在專案中，所有的程式庫的出貨減少專案大小。</span><span class="sxs-lookup"><span data-stu-id="abdb3-250">One of the advantages of using NuGet is that you don't have to ship all the libraries in your project, reducing the project size.</span></span> <span data-ttu-id="abdb3-251">NuGet 的強大工具，請藉由指定封裝版本在 Packages.config 檔案中，您將會成功下載所有必要的程式庫第一次您執行專案。</span><span class="sxs-lookup"><span data-stu-id="abdb3-251">With NuGet Power Tools, by specifying the package versions in the Packages.config file, you will be able to download all the required libraries the first time you run the project.</span></span> <span data-ttu-id="abdb3-252">這就是為什麼您必須從這個實驗室中開啟現有的方案後執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="abdb3-252">This is why you will have to run these steps after you open an existing solution from this lab.</span></span>
3. <span data-ttu-id="abdb3-253">加入新的控制器。</span><span class="sxs-lookup"><span data-stu-id="abdb3-253">Add the new controller.</span></span> <span data-ttu-id="abdb3-254">若要這樣做，請以滑鼠右鍵按一下**控制器**資料夾在方案總管中，選取**新增**然後**控制器**命令。</span><span class="sxs-lookup"><span data-stu-id="abdb3-254">To do this, right-click the **Controllers** folder within the Solution Explorer, select **Add** and then the **Controller** command.</span></span> <span data-ttu-id="abdb3-255">變更**控制器名稱**至*StoreController*，然後按一下**新增**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-255">Change the **Controller Name** to *StoreController*, and click **Add**.</span></span>

    <span data-ttu-id="abdb3-256">![加入控制器 對話方塊](aspnet-mvc-4-fundamentals/_static/image8.png "加入控制器 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="abdb3-256">![Add Controller Dialog](aspnet-mvc-4-fundamentals/_static/image8.png "Add Controller Dialog")</span></span>

    <span data-ttu-id="abdb3-257">*加入控制器 對話方塊*</span><span class="sxs-lookup"><span data-stu-id="abdb3-257">*Add Controller Dialog*</span></span>

<a id="Ex2Task2"></a>

<a id="Task_2_-_Modifying_the_StoreControllers_Actions"></a>
#### <a name="task-2---modifying-the-storecontrollers-actions"></a><span data-ttu-id="abdb3-258">工作 2-修改 StoreController 動作</span><span class="sxs-lookup"><span data-stu-id="abdb3-258">Task 2 - Modifying the StoreController's Actions</span></span>

<span data-ttu-id="abdb3-259">在這個工作中，您將修改呼叫控制器方法**動作**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-259">In this task, you will modify the Controller methods that are called **actions**.</span></span> <span data-ttu-id="abdb3-260">動作是負責處理 URL 要求，以及判斷應該傳送回瀏覽器或叫用的 URL 的使用者的內容。</span><span class="sxs-lookup"><span data-stu-id="abdb3-260">Actions are responsible for handling URL requests and determining the content that should be sent back to the browser or user that invoked the URL.</span></span>

1. <span data-ttu-id="abdb3-261">**StoreController**類別已有**索引**方法。</span><span class="sxs-lookup"><span data-stu-id="abdb3-261">The **StoreController** class already has an **Index** method.</span></span> <span data-ttu-id="abdb3-262">您將稍後在本實驗室中使用它來實作頁面，其中列出音樂存放區的所有內容類型。</span><span class="sxs-lookup"><span data-stu-id="abdb3-262">You will use it later in this Lab to implement the page that lists all genres of the music store.</span></span> <span data-ttu-id="abdb3-263">現在，只要取代**索引**方法傳回的字串為下列程式碼&quot;從 Store.Index() Hello&quot;:</span><span class="sxs-lookup"><span data-stu-id="abdb3-263">For now, just replace the **Index** method with the following code that returns a string &quot;Hello from Store.Index()&quot;:</span></span>

    <span data-ttu-id="abdb3-264">(程式碼片段- *ASP.NET MVC 4 Ex2 StoreController 索引基本概念*)</span><span class="sxs-lookup"><span data-stu-id="abdb3-264">(Code Snippet - *ASP.NET MVC 4 Fundamentals - Ex2 StoreController Index*)</span></span>


    [!code-csharp[Main](aspnet-mvc-4-fundamentals/samples/sample2.cs)]
2. <span data-ttu-id="abdb3-265">新增**瀏覽**和**詳細資料**方法。</span><span class="sxs-lookup"><span data-stu-id="abdb3-265">Add **Browse** and **Details** methods.</span></span> <span data-ttu-id="abdb3-266">若要這樣做，請將加入下列程式碼加入**StoreController**:</span><span class="sxs-lookup"><span data-stu-id="abdb3-266">To do this, add the following code to the **StoreController**:</span></span>

    <span data-ttu-id="abdb3-267">(程式碼片段- *ASP.NET MVC 4 基本概念 Ex2 StoreController BrowseAndDetails*)</span><span class="sxs-lookup"><span data-stu-id="abdb3-267">(Code Snippet - *ASP.NET MVC 4 Fundamentals - Ex2 StoreController BrowseAndDetails*)</span></span>


    [!code-csharp[Main](aspnet-mvc-4-fundamentals/samples/sample3.cs)]

<a id="Ex2Task3"></a>

<a id="Task_3_-_Running_the_Application"></a>
#### <a name="task-3---running-the-application"></a><span data-ttu-id="abdb3-268">工作 3-執行應用程式</span><span class="sxs-lookup"><span data-stu-id="abdb3-268">Task 3 - Running the Application</span></span>

<span data-ttu-id="abdb3-269">在這項工作，您將會嘗試在 web 瀏覽器應用程式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-269">In this task, you will try out the Application in a web browser.</span></span>

1. <span data-ttu-id="abdb3-270">按**F5**執行應用程式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-270">Press **F5** to run the Application.</span></span>
2. <span data-ttu-id="abdb3-271">在專案開始**首頁**頁面。</span><span class="sxs-lookup"><span data-stu-id="abdb3-271">The project starts in the **Home** page.</span></span> <span data-ttu-id="abdb3-272">變更 URL，以確認每個動作實作。</span><span class="sxs-lookup"><span data-stu-id="abdb3-272">Change the URL to verify each action's implementation.</span></span>

    1. <span data-ttu-id="abdb3-273">**/ 儲存**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-273">**/Store**.</span></span> <span data-ttu-id="abdb3-274">您會看到**&quot;從 Store.Index() Hello&quot;**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-274">You will see **&quot;Hello from Store.Index()&quot;**.</span></span>
    2. <span data-ttu-id="abdb3-275">**/ 存放區/瀏覽**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-275">**/Store/Browse**.</span></span> <span data-ttu-id="abdb3-276">您會看到**&quot;從 Store.Browse() Hello&quot;**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-276">You will see **&quot;Hello from Store.Browse()&quot;**.</span></span>
    3. <span data-ttu-id="abdb3-277">**/ 存放區/詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-277">**/Store/Details**.</span></span> <span data-ttu-id="abdb3-278">您會看到**&quot;從 Store.Details() Hello&quot;**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-278">You will see **&quot;Hello from Store.Details()&quot;**.</span></span>

        <span data-ttu-id="abdb3-279">![瀏覽 StoreBrowse](aspnet-mvc-4-fundamentals/_static/image9.png "瀏覽 StoreBrowse")</span><span class="sxs-lookup"><span data-stu-id="abdb3-279">![Browsing StoreBrowse](aspnet-mvc-4-fundamentals/_static/image9.png "Browsing StoreBrowse")</span></span>

        <span data-ttu-id="abdb3-280">*瀏覽 /Store/Browse*</span><span class="sxs-lookup"><span data-stu-id="abdb3-280">*Browsing /Store/Browse*</span></span>
3. <span data-ttu-id="abdb3-281">關閉瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="abdb3-281">Close the browser.</span></span>

<a id="Exercise3"></a>

<a id="Exercise_3_Passing_parameters_to_a_Controller"></a>
### <a name="exercise-3-passing-parameters-to-a-controller"></a><span data-ttu-id="abdb3-282">練習 3： 將參數傳遞至控制器</span><span class="sxs-lookup"><span data-stu-id="abdb3-282">Exercise 3: Passing parameters to a Controller</span></span>

<span data-ttu-id="abdb3-283">到目前為止，您有已傳回常數字串中的控制器。</span><span class="sxs-lookup"><span data-stu-id="abdb3-283">Until now, you have been returning constant strings from the Controllers.</span></span> <span data-ttu-id="abdb3-284">在這個練習中，您將學習如何將參數傳遞至控制器的 URL 和查詢字串，使用，然後以文字回應至瀏覽器的方法動作。</span><span class="sxs-lookup"><span data-stu-id="abdb3-284">In this exercise you will learn how to pass parameters to a Controller using the URL and querystring, and then making the method actions respond with text to the browser.</span></span>

<a id="Ex3Task1"></a>

<a id="Task_1_-_Adding_Genre_Parameter_to_StoreController"></a>
#### <a name="task-1---adding-genre-parameter-to-storecontroller"></a><span data-ttu-id="abdb3-285">工作 1-StoreController 加入類型參數</span><span class="sxs-lookup"><span data-stu-id="abdb3-285">Task 1 - Adding Genre Parameter to StoreController</span></span>

<span data-ttu-id="abdb3-286">在這個工作中，您將使用**querystring**傳送參數到**瀏覽**中的動作方法**StoreController**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-286">In this task, you will use the **querystring** to send parameters to the **Browse** action method in the **StoreController**.</span></span>

1. <span data-ttu-id="abdb3-287">如果尚未開啟，啟動**VS Express for Web**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-287">If not already open, start **VS Express for Web**.</span></span>
2. <span data-ttu-id="abdb3-288">在**檔案**功能表上，選擇**開啟專案**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-288">In the **File** menu, choose **Open Project**.</span></span> <span data-ttu-id="abdb3-289">在 [開啟專案] 對話方塊中，瀏覽至**Source\Ex03 PassingParametersToAController\Begin**，選取**Begin.sln**按一下**開啟**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-289">In the Open Project dialog, browse to **Source\Ex03-PassingParametersToAController\Begin**, select **Begin.sln** and click **Open**.</span></span> <span data-ttu-id="abdb3-290">或者，您可以繼續使用此方案完成上一個練習之後取得。</span><span class="sxs-lookup"><span data-stu-id="abdb3-290">Alternatively, you may continue with the solution that you obtained after completing the previous exercise.</span></span>

    1. <span data-ttu-id="abdb3-291">如果您開啟提供**開始**方案，您必須下載某些遺漏的 NuGet 套件才能繼續。</span><span class="sxs-lookup"><span data-stu-id="abdb3-291">If you opened the provided **Begin** solution, you will need to download some missing NuGet packages before continue.</span></span> <span data-ttu-id="abdb3-292">若要這樣做，請按一下**專案**功能表，然後選取**管理 NuGet 封裝**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-292">To do this, click the **Project** menu and select **Manage NuGet Packages**.</span></span>
    2. <span data-ttu-id="abdb3-293">在**管理 NuGet 封裝**] 對話方塊中，按一下 [**還原**才能下載遺漏的封裝。</span><span class="sxs-lookup"><span data-stu-id="abdb3-293">In the **Manage NuGet Packages** dialog, click **Restore** in order to download missing packages.</span></span>
    3. <span data-ttu-id="abdb3-294">最後，按一下 建置方案**建置** | **建置方案**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-294">Finally, build the solution by clicking **Build** | **Build Solution**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="abdb3-295">使用 NuGet 的優點之一是您不需要在專案中，所有的程式庫的出貨減少專案大小。</span><span class="sxs-lookup"><span data-stu-id="abdb3-295">One of the advantages of using NuGet is that you don't have to ship all the libraries in your project, reducing the project size.</span></span> <span data-ttu-id="abdb3-296">NuGet 的強大工具，請藉由指定封裝版本在 Packages.config 檔案中，您將會成功下載所有必要的程式庫第一次您執行專案。</span><span class="sxs-lookup"><span data-stu-id="abdb3-296">With NuGet Power Tools, by specifying the package versions in the Packages.config file, you will be able to download all the required libraries the first time you run the project.</span></span> <span data-ttu-id="abdb3-297">這就是為什麼您必須從這個實驗室中開啟現有的方案後執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="abdb3-297">This is why you will have to run these steps after you open an existing solution from this lab.</span></span>
3. <span data-ttu-id="abdb3-298">開啟**StoreController**類別。</span><span class="sxs-lookup"><span data-stu-id="abdb3-298">Open **StoreController** class.</span></span> <span data-ttu-id="abdb3-299">若要這樣做，請在**方案總管 中**，依序展開**控制器**資料夾，然後按兩下**StoreController.cs**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-299">To do this, in the **Solution Explorer**, expand the **Controllers** folder and double-click **StoreController.cs**.</span></span>
4. <span data-ttu-id="abdb3-300">變更**瀏覽**方法，將字串參數來要求特定內容類型。</span><span class="sxs-lookup"><span data-stu-id="abdb3-300">Change the **Browse** method, adding a string parameter to request for a specific genre.</span></span> <span data-ttu-id="abdb3-301">ASP.NET MVC 會自動傳遞任何查詢字串或表單張貼參數名稱為**類型**時叫用這個動作方法。</span><span class="sxs-lookup"><span data-stu-id="abdb3-301">ASP.NET MVC will automatically pass any querystring or form post parameters named **genre** to this action method when invoked.</span></span> <span data-ttu-id="abdb3-302">若要這樣做，請取代**瀏覽**方法取代下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="abdb3-302">To do this, replace the **Browse** method with the following code:</span></span>

    <span data-ttu-id="abdb3-303">(程式碼片段- *ASP.NET MVC 4 基本概念 Ex3 StoreController BrowseMethod*)</span><span class="sxs-lookup"><span data-stu-id="abdb3-303">(Code Snippet - *ASP.NET MVC 4 Fundamentals - Ex3 StoreController BrowseMethod*)</span></span>


    [!code-csharp[Main](aspnet-mvc-4-fundamentals/samples/sample4.cs)]

    > [!NOTE]
    > <span data-ttu-id="abdb3-304">您使用**HttpUtility.HtmlEncode**公用程式方法，以防止使用者的連結，例如，將檢視插入的 Javascript   **/存放區/瀏覽？內容類型 =&lt;指令碼&gt;window.location='[http://hackersite.com](http://hackersite.com)'&lt;/指令碼&gt;**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-304">You are using the **HttpUtility.HtmlEncode** utility method to prevents users from injecting Javascript into the View with a link like **/Store/Browse?Genre=&lt;script&gt;window.location='[http://hackersite.com](http://hackersite.com)'&lt;/script&gt;**.</span></span>
    > 
    > <span data-ttu-id="abdb3-305">如需進一步說明，請瀏覽[msdn 本文](https://msdn.microsoft.com/en-us/library/a2a4yykt(v=VS.80).aspx)。</span><span class="sxs-lookup"><span data-stu-id="abdb3-305">For further explanation, please visit [this msdn article](https://msdn.microsoft.com/en-us/library/a2a4yykt(v=VS.80).aspx).</span></span>

<a id="Ex3Task2"></a>

<a id="Task_2_-_Running_the_Application"></a>
#### <a name="task-2---running-the-application"></a><span data-ttu-id="abdb3-306">工作 2-執行應用程式</span><span class="sxs-lookup"><span data-stu-id="abdb3-306">Task 2 - Running the Application</span></span>

<span data-ttu-id="abdb3-307">在這項工作，您將會嘗試在 web 瀏覽器應用程式，並使用**類型**參數。</span><span class="sxs-lookup"><span data-stu-id="abdb3-307">In this task, you will try out the Application in a web browser and use the **genre** parameter.</span></span>

1. <span data-ttu-id="abdb3-308">按**F5**執行應用程式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-308">Press **F5** to run the Application.</span></span>
2. <span data-ttu-id="abdb3-309">在專案開始**首頁**頁面。</span><span class="sxs-lookup"><span data-stu-id="abdb3-309">The project starts in the **Home** page.</span></span> <span data-ttu-id="abdb3-310">將 URL 變更為  */儲存] / [瀏覽？內容類型 = Disco*確認動作接收的類型參數。</span><span class="sxs-lookup"><span data-stu-id="abdb3-310">Change the URL to */Store/Browse?Genre=Disco* to verify that the action receives the genre parameter.</span></span>

    <span data-ttu-id="abdb3-311">![瀏覽 StoreBrowseGenre = Disco](aspnet-mvc-4-fundamentals/_static/image10.png "瀏覽 StoreBrowseGenre = Disco")</span><span class="sxs-lookup"><span data-stu-id="abdb3-311">![Browsing StoreBrowseGenre=Disco](aspnet-mvc-4-fundamentals/_static/image10.png "Browsing StoreBrowseGenre=Disco")</span></span>

    <span data-ttu-id="abdb3-312">*瀏覽 /Store/Browse 嗎？內容類型 = Disco*</span><span class="sxs-lookup"><span data-stu-id="abdb3-312">*Browsing /Store/Browse?Genre=Disco*</span></span>
3. <span data-ttu-id="abdb3-313">關閉瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="abdb3-313">Close the browser.</span></span>

<a id="Ex3Task3"></a>

<a id="Task_3_-_Adding_an_Id_Parameter_Embedded_in_the_URL"></a>
#### <a name="task-3---adding-an-id-parameter-embedded-in-the-url"></a><span data-ttu-id="abdb3-314">工作 3-加入 URL 中內嵌的識別碼參數</span><span class="sxs-lookup"><span data-stu-id="abdb3-314">Task 3 - Adding an Id Parameter Embedded in the URL</span></span>

<span data-ttu-id="abdb3-315">在這個工作中，您將使用**URL**傳遞**識別碼**參數**詳細資料**動作方法的**StoreController**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-315">In this task, you will use the **URL** to pass an **Id** parameter to the **Details** action method of the **StoreController**.</span></span> <span data-ttu-id="abdb3-316">ASP.NET MVC 的預設路由慣例是將 URL 的區段在動作方法名稱後面，名為的參數視為**識別碼**。如果動作方法有名稱為 Id 參數，則 ASP.NET MVC 會自動傳遞的 URL 區段給您做為參數。</span><span class="sxs-lookup"><span data-stu-id="abdb3-316">ASP.NET MVC's default routing convention is to treat the segment of a URL after the action method name as a parameter named **Id**. If your action method has parameter named Id, then ASP.NET MVC will automatically pass the URL segment to you as a parameter.</span></span> <span data-ttu-id="abdb3-317">在 URL 中**5/詳細資料儲存區/**，**識別碼**會被解譯為**5**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-317">In the URL **Store/Details/5**, **Id** will be interpreted as **5**.</span></span>

1. <span data-ttu-id="abdb3-318">變更**詳細資料**方法**StoreController**、 新增**int**參數呼叫**識別碼**。若要這樣做，請取代**詳細資料**方法取代下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="abdb3-318">Change the **Details** method of the **StoreController**, adding an **int** parameter called **id**. To do this, replace the **Details** method with the following code:</span></span>

    <span data-ttu-id="abdb3-319">(程式碼片段- *ASP.NET MVC 4 基本概念 Ex3 StoreController DetailsMethod*)</span><span class="sxs-lookup"><span data-stu-id="abdb3-319">(Code Snippet - *ASP.NET MVC 4 Fundamentals - Ex3 StoreController DetailsMethod*)</span></span>


    [!code-csharp[Main](aspnet-mvc-4-fundamentals/samples/sample5.cs)]

<a id="Ex3Task4"></a>

<a id="Task_4_-_Running_the_Application"></a>
#### <a name="task-4---running-the-application"></a><span data-ttu-id="abdb3-320">工作 4-執行應用程式</span><span class="sxs-lookup"><span data-stu-id="abdb3-320">Task 4 - Running the Application</span></span>

<span data-ttu-id="abdb3-321">在這項工作，您將會嘗試在 web 瀏覽器應用程式，並使用**識別碼**參數。</span><span class="sxs-lookup"><span data-stu-id="abdb3-321">In this task, you will try out the Application in a web browser and use the **Id** parameter.</span></span>

1. <span data-ttu-id="abdb3-322">按**F5**執行應用程式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-322">Press **F5** to run the Application.</span></span>
2. <span data-ttu-id="abdb3-323">在專案開始**首頁**頁面。</span><span class="sxs-lookup"><span data-stu-id="abdb3-323">The project starts in the **Home** page.</span></span> <span data-ttu-id="abdb3-324">將 URL 變更為*/Store/Details/5*確認動作接收 id 參數。</span><span class="sxs-lookup"><span data-stu-id="abdb3-324">Change the URL to */Store/Details/5* to verify that the action receives the id parameter.</span></span>

    <span data-ttu-id="abdb3-325">![瀏覽 StoreDetails5](aspnet-mvc-4-fundamentals/_static/image11.png "瀏覽 StoreDetails5")</span><span class="sxs-lookup"><span data-stu-id="abdb3-325">![Browsing StoreDetails5](aspnet-mvc-4-fundamentals/_static/image11.png "Browsing StoreDetails5")</span></span>

    <span data-ttu-id="abdb3-326">*瀏覽 /Store/Details/5*</span><span class="sxs-lookup"><span data-stu-id="abdb3-326">*Browsing /Store/Details/5*</span></span>

<a id="Exercise4"></a>

<a id="Exercise_4_Creating_a_View"></a>
### <a name="exercise-4-creating-a-view"></a><span data-ttu-id="abdb3-327">練習 4： 建立檢視</span><span class="sxs-lookup"><span data-stu-id="abdb3-327">Exercise 4: Creating a View</span></span>

<span data-ttu-id="abdb3-328">到目前為止您有已傳回字串中的控制器的動作。</span><span class="sxs-lookup"><span data-stu-id="abdb3-328">So far you have been returning strings from controller actions.</span></span> <span data-ttu-id="abdb3-329">雖然是了解控制站的運作方式的實用方式，是不實際的 Web 應用程式如何建立的。</span><span class="sxs-lookup"><span data-stu-id="abdb3-329">Although that is a useful way of understanding how controllers work, it is not how your real Web applications are built.</span></span> <span data-ttu-id="abdb3-330">檢視是提供更好的方法產生 HTML 回到瀏覽器中使用的範本檔案使用的元件。</span><span class="sxs-lookup"><span data-stu-id="abdb3-330">Views are components that provide a better approach for generating HTML back to the browser with the use of template files.</span></span>

<span data-ttu-id="abdb3-331">在這個練習中，您將學習如何加入版面配置主版頁面設定一般的 HTML 內容，來增強網站和最後啟用 HomeController 傳回 HTML 檢視範本的外觀與風格的樣式表的範本。</span><span class="sxs-lookup"><span data-stu-id="abdb3-331">In this exercise you will learn how to add a layout master page to setup a template for common HTML content, a StyleSheet to enhance the look and feel of the site and finally a View template to enable HomeController to return HTML.</span></span>

<a id="Ex4Task1"></a>

<a id="Task_1_-_Modifying_the_file__layoutcshtml"></a>
#### <a name="task-1---modifying-the-file-layoutcshtml"></a><span data-ttu-id="abdb3-332">工作 1-修改檔案\_layout.cshtml</span><span class="sxs-lookup"><span data-stu-id="abdb3-332">Task 1 - Modifying the file \_layout.cshtml</span></span>

<span data-ttu-id="abdb3-333">檔案**~/Views/Shared/\_layout.cshtml**可讓您設定一般 HTML 橫跨整個網站使用的範本。</span><span class="sxs-lookup"><span data-stu-id="abdb3-333">The file **~/Views/Shared/\_layout.cshtml** allows you to setup a template for common HTML to use across the entire website.</span></span> <span data-ttu-id="abdb3-334">在這項工作中，您將會配置主版頁面的連結的通用標頭加入首頁並儲存區的區域中。</span><span class="sxs-lookup"><span data-stu-id="abdb3-334">In this task you will add a layout master page with a common header with links to the Home page and Store area.</span></span>

1. <span data-ttu-id="abdb3-335">如果尚未開啟，啟動**VS Express for Web**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-335">If not already open, start **VS Express for Web**.</span></span>
2. <span data-ttu-id="abdb3-336">在**檔案**功能表上，選擇**開啟專案**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-336">In the **File** menu, choose **Open Project**.</span></span> <span data-ttu-id="abdb3-337">在 [開啟專案] 對話方塊中，瀏覽至**Source\Ex04 CreatingAView\Begin**，選取**Begin.sln**按一下**開啟**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-337">In the Open Project dialog, browse to **Source\Ex04-CreatingAView\Begin**, select **Begin.sln** and click **Open**.</span></span> <span data-ttu-id="abdb3-338">或者，您可以繼續使用此方案完成上一個練習之後取得。</span><span class="sxs-lookup"><span data-stu-id="abdb3-338">Alternatively, you may continue with the solution that you obtained after completing the previous exercise.</span></span>

    1. <span data-ttu-id="abdb3-339">如果您開啟提供**開始**方案，您必須下載某些遺漏的 NuGet 套件才能繼續。</span><span class="sxs-lookup"><span data-stu-id="abdb3-339">If you opened the provided **Begin** solution, you will need to download some missing NuGet packages before continue.</span></span> <span data-ttu-id="abdb3-340">若要這樣做，請按一下**專案**功能表，然後選取**管理 NuGet 封裝**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-340">To do this, click the **Project** menu and select **Manage NuGet Packages**.</span></span>
    2. <span data-ttu-id="abdb3-341">在**管理 NuGet 封裝**] 對話方塊中，按一下 [**還原**才能下載遺漏的封裝。</span><span class="sxs-lookup"><span data-stu-id="abdb3-341">In the **Manage NuGet Packages** dialog, click **Restore** in order to download missing packages.</span></span>
    3. <span data-ttu-id="abdb3-342">最後，按一下 建置方案**建置** | **建置方案**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-342">Finally, build the solution by clicking **Build** | **Build Solution**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="abdb3-343">使用 NuGet 的優點之一是您不需要在專案中，所有的程式庫的出貨減少專案大小。</span><span class="sxs-lookup"><span data-stu-id="abdb3-343">One of the advantages of using NuGet is that you don't have to ship all the libraries in your project, reducing the project size.</span></span> <span data-ttu-id="abdb3-344">NuGet 的強大工具，請藉由指定封裝版本在 Packages.config 檔案中，您將會成功下載所有必要的程式庫第一次您執行專案。</span><span class="sxs-lookup"><span data-stu-id="abdb3-344">With NuGet Power Tools, by specifying the package versions in the Packages.config file, you will be able to download all the required libraries the first time you run the project.</span></span> <span data-ttu-id="abdb3-345">這就是為什麼您必須從這個實驗室中開啟現有的方案後執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="abdb3-345">This is why you will have to run these steps after you open an existing solution from this lab.</span></span>
3. <span data-ttu-id="abdb3-346">檔案 **\_layout.cshtml**包含站台上的所有頁面的 HTML 容器版面配置。</span><span class="sxs-lookup"><span data-stu-id="abdb3-346">The file **\_layout.cshtml** contains the HTML container layout for all pages on the site.</span></span> <span data-ttu-id="abdb3-347">它包含 **&lt;html&gt;**  HTML 回應中，項目，以及 **&lt;head&gt;** 和**&lt;主體&gt;**項目。</span><span class="sxs-lookup"><span data-stu-id="abdb3-347">It includes the **&lt;html&gt;** element for the HTML response, as well as the **&lt;head&gt;** and **&lt;body&gt;** elements.</span></span> <span data-ttu-id="abdb3-348">**@RenderBody（)** HTML 中主體識別區域，檢視範本可以填入動態內容。</span><span class="sxs-lookup"><span data-stu-id="abdb3-348">**@RenderBody()** within the HTML body identify regions that view templates will be able to fill in with dynamic content.</span></span>
<span data-ttu-id="abdb3-349">(C#)</span><span class="sxs-lookup"><span data-stu-id="abdb3-349">(C#)</span></span>

    [!code-cshtml[Main](aspnet-mvc-4-fundamentals/samples/sample6.cshtml)]
4. <span data-ttu-id="abdb3-350">將連結的通用標頭加入首頁並儲存區域之站台中的所有頁面。</span><span class="sxs-lookup"><span data-stu-id="abdb3-350">Add a common header with links to the Home page and Store area on all pages in the site.</span></span> <span data-ttu-id="abdb3-351">若要這樣做，請加入下列程式碼下方&lt;主體&gt;陳述式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-351">In order to do that, add the following code below &lt;body&gt; statement.</span></span>
<span data-ttu-id="abdb3-352">(C#)</span><span class="sxs-lookup"><span data-stu-id="abdb3-352">(C#)</span></span>

    [!code-cshtml[Main](aspnet-mvc-4-fundamentals/samples/sample7.cshtml)]
5. <span data-ttu-id="abdb3-353">包含要呈現的每個頁面的 [主體] 區段的 div。</span><span class="sxs-lookup"><span data-stu-id="abdb3-353">Include a div to render the body section of each page.</span></span> <span data-ttu-id="abdb3-354">取代 **@RenderBody（)**下列 higlighted 程式碼: (C#)</span><span class="sxs-lookup"><span data-stu-id="abdb3-354">Replace **@RenderBody()** with the following higlighted code: (C#)</span></span>

    [!code-cshtml[Main](aspnet-mvc-4-fundamentals/samples/sample8.cshtml)]

    > [!NOTE]
    > <span data-ttu-id="abdb3-355">您知道嗎？</span><span class="sxs-lookup"><span data-stu-id="abdb3-355">Did you know?</span></span> <span data-ttu-id="abdb3-356">Visual Studio 2012 會有片段，可讓您輕鬆將常用的程式碼加入 HTML、 程式碼檔案和更多 ！</span><span class="sxs-lookup"><span data-stu-id="abdb3-356">Visual Studio 2012 has snippets that make it easy to add commonly used code in HTML, code files and more!</span></span> <span data-ttu-id="abdb3-357">試試看輸入 **&lt;div&gt;** 按 **索引標籤**兩次，插入完整**div**標記。</span><span class="sxs-lookup"><span data-stu-id="abdb3-357">Try it out by typing **&lt;div&gt;** and pressing **TAB** twice to insert a complete **div** tag.</span></span>

<a id="Ex4Task2"></a>

<a id="Task_2_-_Adding_CSS_Stylesheet"></a>
#### <a name="task-2---adding-css-stylesheet"></a><span data-ttu-id="abdb3-358">工作 2-將 CSS 樣式表</span><span class="sxs-lookup"><span data-stu-id="abdb3-358">Task 2 - Adding CSS Stylesheet</span></span>

<span data-ttu-id="abdb3-359">空白專案範本包含非常簡化的 CSS 檔案只包含用來顯示基本形式與驗證訊息的樣式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-359">The empty project template includes a very streamlined CSS file which just includes styles used to display basic forms and validation messages.</span></span> <span data-ttu-id="abdb3-360">若要加強網站的外觀與風格，您將使用其他的 CSS 和圖像 （可能是由設計工具提供）。</span><span class="sxs-lookup"><span data-stu-id="abdb3-360">You will use additional CSS and images (potentially provided by a designer) in order to enhance the look and feel of the site.</span></span>

<span data-ttu-id="abdb3-361">在這個工作中，您會將定義站台的樣式的 CSS 樣式表。</span><span class="sxs-lookup"><span data-stu-id="abdb3-361">In this task, you will add a CSS stylesheet to define the styles of the site.</span></span>

1. <span data-ttu-id="abdb3-362">CSS 檔案和映像會包含在**Source\Assets\Content**本實驗室的資料夾。</span><span class="sxs-lookup"><span data-stu-id="abdb3-362">The CSS file and images are included in the **Source\Assets\Content** folder of this Lab.</span></span> <span data-ttu-id="abdb3-363">以便將它們新增至應用程式，將其內容從**Windows 檔案總管**到視窗**方案總管 中**在 Visual Studio Express for Web，如下所示：</span><span class="sxs-lookup"><span data-stu-id="abdb3-363">In order to add them to the application, drag their content from a **Windows Explorer** window into the **Solution Explorer** in Visual Studio Express for Web, as shown below:</span></span>

    <span data-ttu-id="abdb3-364">![拖曳樣式內容](aspnet-mvc-4-fundamentals/_static/image12.png "拖曳樣式內容")</span><span class="sxs-lookup"><span data-stu-id="abdb3-364">![Dragging style contents](aspnet-mvc-4-fundamentals/_static/image12.png "Dragging style contents")</span></span>

    <span data-ttu-id="abdb3-365">*拖曳樣式內容*</span><span class="sxs-lookup"><span data-stu-id="abdb3-365">*Dragging style contents*</span></span>
2. <span data-ttu-id="abdb3-366">警告會出現一個對話方塊，詢問確認是否要取代**Site.css**檔案和一些現有的映像。</span><span class="sxs-lookup"><span data-stu-id="abdb3-366">A warning dialog will appear, asking for confirmation to replace **Site.css** file and some existing images.</span></span> <span data-ttu-id="abdb3-367">請檢查**套用至所有項目**按一下**是**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-367">Check **Apply to all items** and click **Yes**.</span></span>

<a id="Ex4Task3"></a>

<a id="Task_3_-_Adding_a_View_Template"></a>
#### <a name="task-3---adding-a-view-template"></a><span data-ttu-id="abdb3-368">工作 3-新增檢視範本</span><span class="sxs-lookup"><span data-stu-id="abdb3-368">Task 3 - Adding a View Template</span></span>

<span data-ttu-id="abdb3-369">在這項工作，您會加入檢視範本產生將會使用配置主版頁面的 HTML 回應，並在此練習中，加入 CSS。</span><span class="sxs-lookup"><span data-stu-id="abdb3-369">In this task, you will add a View template to generate the HTML response that will use the layout master page and CSS added in this exercise.</span></span>

1. <span data-ttu-id="abdb3-370">若要瀏覽網站的首頁上時，請使用檢視範本，您首先需要而不是傳回字串，表示**HomeController 索引**方法會傳回**檢視**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-370">To use a View template when browsing the site's home page, you will first need to indicate that instead of returning a string, the **HomeController Index** method will return a **View**.</span></span> <span data-ttu-id="abdb3-371">開啟**HomeController**類別，並變更其**索引**方法以傳回**ActionResult**，並讓它傳回**View()**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-371">Open **HomeController** class and change its **Index** method to return an **ActionResult**, and have it return **View()**.</span></span>

    <span data-ttu-id="abdb3-372">(程式碼片段- *ASP.NET MVC 4 Ex4 HomeController 索引基本概念*)</span><span class="sxs-lookup"><span data-stu-id="abdb3-372">(Code Snippet - *ASP.NET MVC 4 Fundamentals - Ex4 HomeController Index*)</span></span>


    [!code-csharp[Main](aspnet-mvc-4-fundamentals/samples/sample9.cs)]
2. <span data-ttu-id="abdb3-373">現在，您需要加入適當的檢視範本。</span><span class="sxs-lookup"><span data-stu-id="abdb3-373">Now, you need to add an appropriate View template.</span></span> <span data-ttu-id="abdb3-374">若要這樣做，**以滑鼠右鍵按一下**內**索引**動作方法，然後選取**加入檢視**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-374">To do this, **right-click** inside the **Index** action method and select **Add View**.</span></span> <span data-ttu-id="abdb3-375">這會顯示**加入檢視**對話方塊。</span><span class="sxs-lookup"><span data-stu-id="abdb3-375">This will bring up the **Add View** dialog.</span></span>

    <span data-ttu-id="abdb3-376">![加入從索引方法內的檢視](aspnet-mvc-4-fundamentals/_static/image13.png "加入從索引方法內的檢視")</span><span class="sxs-lookup"><span data-stu-id="abdb3-376">![Adding a View from within the Index method](aspnet-mvc-4-fundamentals/_static/image13.png "Adding a View from within the Index method")</span></span>

    <span data-ttu-id="abdb3-377">*加入從索引方法內的檢視*</span><span class="sxs-lookup"><span data-stu-id="abdb3-377">*Adding a View from within the Index method*</span></span>
3. <span data-ttu-id="abdb3-378">**加入檢視**產生檢視的範本檔案會出現對話方塊。</span><span class="sxs-lookup"><span data-stu-id="abdb3-378">The **Add View** Dialog will appear to generate a View template file.</span></span> <span data-ttu-id="abdb3-379">根據預設，這個對話方塊會預先填入的檢視表範本的名稱，使其符合使用它的動作方法。</span><span class="sxs-lookup"><span data-stu-id="abdb3-379">By default, this dialog pre-populates the name of the View template so that it matches the action method that will use it.</span></span> <span data-ttu-id="abdb3-380">因為您使用**加入檢視**內的內容功能表**索引**動作方法內 HomeController**加入檢視**對話方塊有做為預設檢視名稱的索引。</span><span class="sxs-lookup"><span data-stu-id="abdb3-380">Because you used the **Add View** context menu within the **Index** action method within the HomeController, the **Add View** dialog has Index as the default view name.</span></span> <span data-ttu-id="abdb3-381">按一下 [加入] 。</span><span class="sxs-lookup"><span data-stu-id="abdb3-381">Click **Add**.</span></span>

    <span data-ttu-id="abdb3-382">![新增檢視對話方塊](aspnet-mvc-4-fundamentals/_static/image14.png "新增檢視對話方塊")</span><span class="sxs-lookup"><span data-stu-id="abdb3-382">![Add View Dialog](aspnet-mvc-4-fundamentals/_static/image14.png "Add View Dialog")</span></span>

    <span data-ttu-id="abdb3-383">*新增檢視對話方塊*</span><span class="sxs-lookup"><span data-stu-id="abdb3-383">*Add View Dialog*</span></span>
4. <span data-ttu-id="abdb3-384">Visual Studio 會產生**Index.cshtml**內檢視範本**Views\Home**資料夾，然後開啟它。</span><span class="sxs-lookup"><span data-stu-id="abdb3-384">Visual Studio generates an **Index.cshtml** view template inside the **Views\Home** folder and then opens it.</span></span>

    <span data-ttu-id="abdb3-385">![首頁建立的索引檢視表](aspnet-mvc-4-fundamentals/_static/image15.png "建立首頁索引檢視表")</span><span class="sxs-lookup"><span data-stu-id="abdb3-385">![Home Index view created](aspnet-mvc-4-fundamentals/_static/image15.png "Home Index view created")</span></span>

    <span data-ttu-id="abdb3-386">*建立主索引檢視表*</span><span class="sxs-lookup"><span data-stu-id="abdb3-386">*Home Index view created*</span></span>

    > [!NOTE]
    > <span data-ttu-id="abdb3-387">名稱和位置**Index.cshtml**檔案相關，而且依照預設的 ASP.NET MVC 命名慣例。</span><span class="sxs-lookup"><span data-stu-id="abdb3-387">name and location of the **Index.cshtml** file is relevant and follows the default ASP.NET MVC naming conventions.</span></span>
    > 
    > <span data-ttu-id="abdb3-388">資料夾 \Views\**首頁** 符合控制器名稱 (**首頁**控制站)。</span><span class="sxs-lookup"><span data-stu-id="abdb3-388">The folder \Views\**Home** matches the controller name (**Home** Controller).</span></span> <span data-ttu-id="abdb3-389">檢視範本名稱 (**索引**)，符合控制器動作方法，這個方法會將所顯示的檢視。</span><span class="sxs-lookup"><span data-stu-id="abdb3-389">The View template name (**Index**), matches the controller action method which will be displaying the View.</span></span>
    > 
    > <span data-ttu-id="abdb3-390">如此一來，可避免 ASP.NET MVC，必須使用下列命名慣例，傳回檢視時，明確指定的名稱或檢視表範本的位置。</span><span class="sxs-lookup"><span data-stu-id="abdb3-390">This way, ASP.NET MVC avoids having to explicitly specify the name or location of a View template when using this naming convention to return a View.</span></span>
5. <span data-ttu-id="abdb3-391">產生的檢視範本根據 **\_layout.cshtml**先前定義的範本。</span><span class="sxs-lookup"><span data-stu-id="abdb3-391">The generated View template is based on the **\_layout.cshtml** template earlier defined.</span></span> <span data-ttu-id="abdb3-392">要更新 ViewBag.Title 屬性**首頁**，並將變更的主要內容**這是在首頁上**，如下列程式碼所示：</span><span class="sxs-lookup"><span data-stu-id="abdb3-392">Update the ViewBag.Title property to **Home**, and change the main content to **This is the Home Page**, as shown in the code below:</span></span>


    [!code-cshtml[Main](aspnet-mvc-4-fundamentals/samples/sample10.cshtml)]
6. <span data-ttu-id="abdb3-393">選取**MvcMusicStore**專案在 [方案總管]，然後按**F5**執行應用程式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-393">Select **MvcMusicStore** project in the Solution Explorer and Press **F5** to run the Application.</span></span>

<a id="Ex4Task4"></a>

<a id="Task_4_Verification"></a>
#### <a name="task-4-verification"></a><span data-ttu-id="abdb3-394">工作 4： 驗證</span><span class="sxs-lookup"><span data-stu-id="abdb3-394">Task 4: Verification</span></span>

<span data-ttu-id="abdb3-395">若要確認您已經正確地執行所有的步驟，在上一個練習中，可以繼續執行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="abdb3-395">In order to verify that you have correctly performed all the steps in the previous exercise, proceed as follows:</span></span>

<span data-ttu-id="abdb3-396">在瀏覽器中開啟應用程式時，您應該注意到：</span><span class="sxs-lookup"><span data-stu-id="abdb3-396">With the application opened in a browser, you should note that:</span></span>

1. <span data-ttu-id="abdb3-397">HomeController 索引動作方法找到並顯示**\Views\Home\Index.cshtml**檢視範本，即使程式碼呼叫**傳回 View()**，因為接下來檢視範本標準的命名慣例。</span><span class="sxs-lookup"><span data-stu-id="abdb3-397">The HomeController's Index action method found and displayed the **\Views\Home\Index.cshtml** View template, even though the code called **return View()**, because the View template followed the standard naming convention.</span></span>
2. <span data-ttu-id="abdb3-398">首頁會顯示歡迎訊息內定義**\Views\Home\Index.cshtml**檢視範本。</span><span class="sxs-lookup"><span data-stu-id="abdb3-398">The Home Page displays the welcome message defined within the **\Views\Home\Index.cshtml** view template.</span></span>
3. <span data-ttu-id="abdb3-399">使用 [首頁]  **\_layout.cshtml**範本，因此歡迎訊息是否包含在標準網站 HTML 版面配置。</span><span class="sxs-lookup"><span data-stu-id="abdb3-399">The Home Page is using the **\_layout.cshtml** template, and so the welcome message is contained within the standard site HTML layout.</span></span>

    <span data-ttu-id="abdb3-400">![首頁索引檢視，使用定義 LayoutPage 和樣式](aspnet-mvc-4-fundamentals/_static/image16.png "首頁索引檢視，使用定義 LayoutPage 和樣式")</span><span class="sxs-lookup"><span data-stu-id="abdb3-400">![Home Index View using the defined LayoutPage and style](aspnet-mvc-4-fundamentals/_static/image16.png "Home Index View using the defined LayoutPage and style")</span></span>

    <span data-ttu-id="abdb3-401">*使用 LayoutPage 和樣式定義的主索引檢視*</span><span class="sxs-lookup"><span data-stu-id="abdb3-401">*Home Index View using the defined LayoutPage and style*</span></span>

<a id="Exercise5"></a>

<a id="Exercise_5_Creating_a_View_Model"></a>
### <a name="exercise-5-creating-a-view-model"></a><span data-ttu-id="abdb3-402">練習 5： 建立檢視模型</span><span class="sxs-lookup"><span data-stu-id="abdb3-402">Exercise 5: Creating a View Model</span></span>

<span data-ttu-id="abdb3-403">目前為止，您進行檢視顯示硬式編碼的 HTML，但若要建立動態 web 應用程式，檢視範本應該從控制器接收資訊。</span><span class="sxs-lookup"><span data-stu-id="abdb3-403">So far, you made your Views display hardcoded HTML, but, in order to create dynamic web applications, the View template should receive information from the Controller.</span></span> <span data-ttu-id="abdb3-404">要用於該目的的一個常用的技巧是**ViewModel**模式，它會讓控制器能夠封裝產生適當的 HTML 回應所需的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="abdb3-404">One common technique to be used for that purpose is the **ViewModel** pattern, which allows a Controller to package up all the information needed to generate the appropriate HTML response.</span></span>

<span data-ttu-id="abdb3-405">在此練習中，您將學習如何建立 ViewModel 類別並新增必要的屬性： 的存放區，這些內容類型清單中的內容類型的數目。</span><span class="sxs-lookup"><span data-stu-id="abdb3-405">In this exercise, you will learn how to create a ViewModel class and add the required properties: the number of genres in the store and a list of those genres.</span></span> <span data-ttu-id="abdb3-406">您也會更新以使用建立的 ViewModel，StoreController，最後，您將建立新的檢視表範本以顯示頁面所述的屬性。</span><span class="sxs-lookup"><span data-stu-id="abdb3-406">You will also update the StoreController to use the created ViewModel, and finally, you will create a new View template that will display the mentioned properties in the page.</span></span>

<a id="Ex5Task1"></a>

<a id="Task_1_-_Creating_a_ViewModel_Class"></a>
#### <a name="task-1---creating-a-viewmodel-class"></a><span data-ttu-id="abdb3-407">工作 1-建立 ViewModel 類別</span><span class="sxs-lookup"><span data-stu-id="abdb3-407">Task 1 - Creating a ViewModel Class</span></span>

<span data-ttu-id="abdb3-408">在這項工作，您將建立會實作儲存區的內容類型清單案例 ViewModel 類別。</span><span class="sxs-lookup"><span data-stu-id="abdb3-408">In this task, you will create a ViewModel class that will implement the Store genre listing scenario.</span></span>

1. <span data-ttu-id="abdb3-409">如果尚未開啟，啟動**VS Express for Web**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-409">If not already open, start **VS Express for Web**.</span></span>
2. <span data-ttu-id="abdb3-410">在**檔案**功能表上，選擇**開啟專案**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-410">In the **File** menu, choose **Open Project**.</span></span> <span data-ttu-id="abdb3-411">在 [開啟專案] 對話方塊中，瀏覽至**Source\Ex05 CreatingAViewModel\Begin**，選取**Begin.sln**按一下**開啟**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-411">In the Open Project dialog, browse to **Source\Ex05-CreatingAViewModel\Begin**, select **Begin.sln** and click **Open**.</span></span> <span data-ttu-id="abdb3-412">或者，您可以繼續使用此方案完成上一個練習之後取得。</span><span class="sxs-lookup"><span data-stu-id="abdb3-412">Alternatively, you may continue with the solution that you obtained after completing the previous exercise.</span></span>

    1. <span data-ttu-id="abdb3-413">如果您開啟提供**開始**方案，您必須下載某些遺漏的 NuGet 套件才能繼續。</span><span class="sxs-lookup"><span data-stu-id="abdb3-413">If you opened the provided **Begin** solution, you will need to download some missing NuGet packages before continue.</span></span> <span data-ttu-id="abdb3-414">若要這樣做，請按一下**專案**功能表，然後選取**管理 NuGet 封裝**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-414">To do this, click the **Project** menu and select **Manage NuGet Packages**.</span></span>
    2. <span data-ttu-id="abdb3-415">在**管理 NuGet 封裝**] 對話方塊中，按一下 [**還原**才能下載遺漏的封裝。</span><span class="sxs-lookup"><span data-stu-id="abdb3-415">In the **Manage NuGet Packages** dialog, click **Restore** in order to download missing packages.</span></span>
    3. <span data-ttu-id="abdb3-416">最後，按一下 建置方案**建置** | **建置方案**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-416">Finally, build the solution by clicking **Build** | **Build Solution**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="abdb3-417">使用 NuGet 的優點之一是您不需要在專案中，所有的程式庫的出貨減少專案大小。</span><span class="sxs-lookup"><span data-stu-id="abdb3-417">One of the advantages of using NuGet is that you don't have to ship all the libraries in your project, reducing the project size.</span></span> <span data-ttu-id="abdb3-418">NuGet 的強大工具，請藉由指定封裝版本在 Packages.config 檔案中，您將會成功下載所有必要的程式庫第一次您執行專案。</span><span class="sxs-lookup"><span data-stu-id="abdb3-418">With NuGet Power Tools, by specifying the package versions in the Packages.config file, you will be able to download all the required libraries the first time you run the project.</span></span> <span data-ttu-id="abdb3-419">這就是為什麼您必須從這個實驗室中開啟現有的方案後執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="abdb3-419">This is why you will have to run these steps after you open an existing solution from this lab.</span></span>
3. <span data-ttu-id="abdb3-420">建立**ViewModels**保留 ViewModel 資料夾。</span><span class="sxs-lookup"><span data-stu-id="abdb3-420">Create a **ViewModels** folder to hold the ViewModel.</span></span> <span data-ttu-id="abdb3-421">若要這樣做，以滑鼠右鍵按一下最上層**MvcMusicStore**專案，然後選取**新增**然後**新資料夾**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-421">To do this, right-click the top-level **MvcMusicStore** project, select **Add** and then **New Folder**.</span></span>

    <span data-ttu-id="abdb3-422">![加入新的資料夾](aspnet-mvc-4-fundamentals/_static/image17.png "加入新的資料夾")</span><span class="sxs-lookup"><span data-stu-id="abdb3-422">![Adding a new folder](aspnet-mvc-4-fundamentals/_static/image17.png "Adding a new folder")</span></span>

    <span data-ttu-id="abdb3-423">*加入新的資料夾*</span><span class="sxs-lookup"><span data-stu-id="abdb3-423">*Adding a new folder*</span></span>
4. <span data-ttu-id="abdb3-424">將資料夾命名為*ViewModels*。</span><span class="sxs-lookup"><span data-stu-id="abdb3-424">Name the folder *ViewModels*.</span></span>

    <span data-ttu-id="abdb3-425">![在 方案總管 ViewModels 資料夾](aspnet-mvc-4-fundamentals/_static/image18.png "ViewModels 資料夾在 方案總管")</span><span class="sxs-lookup"><span data-stu-id="abdb3-425">![ViewModels folder in Solution Explorer](aspnet-mvc-4-fundamentals/_static/image18.png "ViewModels folder in Solution Explorer")</span></span>

    <span data-ttu-id="abdb3-426">*在 方案總管 ViewModels 資料夾*</span><span class="sxs-lookup"><span data-stu-id="abdb3-426">*ViewModels folder in Solution Explorer*</span></span>
5. <span data-ttu-id="abdb3-427">建立**ViewModel**類別。</span><span class="sxs-lookup"><span data-stu-id="abdb3-427">Create a **ViewModel** class.</span></span> <span data-ttu-id="abdb3-428">若要這樣做，以滑鼠右鍵按一下**ViewModels**最近建立資料夾，選取**新增**然後**新項目**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-428">To do this, right-click on the **ViewModels** folder recently created, select **Add** and then **New Item**.</span></span> <span data-ttu-id="abdb3-429">在下**程式碼**，選擇**類別**項目，並將檔案命名*StoreIndexViewModel.cs*，然後按一下 **新增**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-429">Under **Code**, choose the **Class** item and name the file *StoreIndexViewModel.cs*, then click **Add**.</span></span>

    <span data-ttu-id="abdb3-430">![加入新類別](aspnet-mvc-4-fundamentals/_static/image19.png "加入新類別")</span><span class="sxs-lookup"><span data-stu-id="abdb3-430">![Adding a new Class](aspnet-mvc-4-fundamentals/_static/image19.png "Adding a new Class")</span></span>

    <span data-ttu-id="abdb3-431">*加入新類別*</span><span class="sxs-lookup"><span data-stu-id="abdb3-431">*Adding a new Class*</span></span>

    <span data-ttu-id="abdb3-432">![建立 StoreIndexViewModel 類別](aspnet-mvc-4-fundamentals/_static/image20.png "建立 StoreIndexViewModel 類別")</span><span class="sxs-lookup"><span data-stu-id="abdb3-432">![Creating StoreIndexViewModel class](aspnet-mvc-4-fundamentals/_static/image20.png "Creating StoreIndexViewModel class")</span></span>

    <span data-ttu-id="abdb3-433">*建立 StoreIndexViewModel 類別*</span><span class="sxs-lookup"><span data-stu-id="abdb3-433">*Creating StoreIndexViewModel class*</span></span>

<a id="Ex5Task2"></a>

<a id="Task_2_-_Adding_Properties_to_the_ViewModel_class"></a>
#### <a name="task-2---adding-properties-to-the-viewmodel-class"></a><span data-ttu-id="abdb3-434">工作 2-新增屬性到 ViewModel 類別</span><span class="sxs-lookup"><span data-stu-id="abdb3-434">Task 2 - Adding Properties to the ViewModel class</span></span>

<span data-ttu-id="abdb3-435">有兩個參數來傳遞 StoreController 檢視範本以產生預期的 HTML 回應： 的存放區，這些內容類型清單中的內容類型的數目。</span><span class="sxs-lookup"><span data-stu-id="abdb3-435">There are two parameters to be passed from the StoreController to the View template in order to generate the expected HTML response: the number of genres in the store and a list of those genres.</span></span>

<span data-ttu-id="abdb3-436">在這個工作中，您會將這些 2 屬性**StoreIndexViewModel**類別： **NumberOfGenres** （整數） 和**內容類型**（字串的清單）。</span><span class="sxs-lookup"><span data-stu-id="abdb3-436">In this task, you will add those 2 properties to the **StoreIndexViewModel** class: **NumberOfGenres** (an integer) and **Genres** (a list of strings).</span></span>

1. <span data-ttu-id="abdb3-437">新增**NumberOfGenres**和**內容類型**屬性**StoreIndexViewModel**類別。</span><span class="sxs-lookup"><span data-stu-id="abdb3-437">Add **NumberOfGenres** and **Genres** properties to the **StoreIndexViewModel** class.</span></span> <span data-ttu-id="abdb3-438">若要這樣做，請加入下列 2 行至類別定義：</span><span class="sxs-lookup"><span data-stu-id="abdb3-438">To do this, add the following 2 lines to the class definition:</span></span>

    <span data-ttu-id="abdb3-439">(程式碼片段- *ASP.NET MVC 4 基礎 Ex5 StoreIndexViewModel 屬性*)</span><span class="sxs-lookup"><span data-stu-id="abdb3-439">(Code Snippet - *ASP.NET MVC 4 Fundamentals - Ex5 StoreIndexViewModel properties*)</span></span>


    [!code-csharp[Main](aspnet-mvc-4-fundamentals/samples/sample11.cs)]

    > [!NOTE]
    > <span data-ttu-id="abdb3-440">**{Get; 設定;}**標記法會使用 C# 功能自動實作的屬性。</span><span class="sxs-lookup"><span data-stu-id="abdb3-440">The **{ get; set; }** notation makes use of C#'s auto-implemented properties feature.</span></span> <span data-ttu-id="abdb3-441">它提供屬性的優點，而不需要我們宣告支援欄位。</span><span class="sxs-lookup"><span data-stu-id="abdb3-441">It provides the benefits of a property without requiring us to declare a backing field.</span></span>

<a id="Ex5Task3"></a>

<a id="Task_3_-_Updating_StoreController_to_use_the_StoreIndexViewModel"></a>
#### <a name="task-3---updating-storecontroller-to-use-the-storeindexviewmodel"></a><span data-ttu-id="abdb3-442">工作 3-更新 StoreController 使用 StoreIndexViewModel</span><span class="sxs-lookup"><span data-stu-id="abdb3-442">Task 3 - Updating StoreController to use the StoreIndexViewModel</span></span>

<span data-ttu-id="abdb3-443">**StoreIndexViewModel**類別會封裝將從傳遞所需的資訊**StoreController**的**索引**方法，以便在產生回應的檢視範本.</span><span class="sxs-lookup"><span data-stu-id="abdb3-443">The **StoreIndexViewModel** class encapsulates the information needed to pass from **StoreController**'s **Index** method to a View template in order to generate a response.</span></span>

<span data-ttu-id="abdb3-444">在這項工作，您將更新**StoreController**使用**StoreIndexViewModel**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-444">In this task, you will update the **StoreController** to use the **StoreIndexViewModel**.</span></span>

1. <span data-ttu-id="abdb3-445">開啟**StoreController**類別。</span><span class="sxs-lookup"><span data-stu-id="abdb3-445">Open **StoreController** class.</span></span>

    <span data-ttu-id="abdb3-446">![開啟 StoreController 類別](aspnet-mvc-4-fundamentals/_static/image21.png "開啟 StoreController 類別")</span><span class="sxs-lookup"><span data-stu-id="abdb3-446">![Opening StoreController class](aspnet-mvc-4-fundamentals/_static/image21.png "Opening StoreController class")</span></span>

    <span data-ttu-id="abdb3-447">*開啟 StoreController 類別*</span><span class="sxs-lookup"><span data-stu-id="abdb3-447">*Opening StoreController class*</span></span>
2. <span data-ttu-id="abdb3-448">若要使用**StoreIndexViewModel**類別從**StoreController**的最上方加入下列命名空間**StoreController**程式碼：</span><span class="sxs-lookup"><span data-stu-id="abdb3-448">In order to use the **StoreIndexViewModel** class from the **StoreController**, add the following namespace at the top of the **StoreController** code:</span></span>

    <span data-ttu-id="abdb3-449">(程式碼片段- *ASP.NET MVC 4 基礎 Ex5 StoreIndexViewModel 使用 ViewModels*)</span><span class="sxs-lookup"><span data-stu-id="abdb3-449">(Code Snippet - *ASP.NET MVC 4 Fundamentals - Ex5 StoreIndexViewModel using ViewModels*)</span></span>


    [!code-csharp[Main](aspnet-mvc-4-fundamentals/samples/sample12.cs)]
3. <span data-ttu-id="abdb3-450">變更**StoreController**的**索引**動作方法，使它建立並填入**StoreIndexViewModel**物件，並再將它，傳遞至檢視範本產生 HTML 的回應。</span><span class="sxs-lookup"><span data-stu-id="abdb3-450">Change the **StoreController**'s **Index** action method so that it creates and populates a **StoreIndexViewModel** object and then passes it off to a View template to generate an HTML response with it.</span></span>

    > [!NOTE]
    > <span data-ttu-id="abdb3-451">在實驗室中&quot;ASP.NET MVC 模型和資料存取&quot;您將撰寫程式碼，從資料庫擷取的存放區的內容類型清單。</span><span class="sxs-lookup"><span data-stu-id="abdb3-451">In Lab &quot;ASP.NET MVC Models and Data Access&quot; you will write code that retrieves the list of store genres from a database.</span></span> <span data-ttu-id="abdb3-452">在下列程式碼中，您將建立**清單**虛擬資料內容類型，將會填入**StoreIndexViewModel**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-452">In the following code, you will create a **List** of dummy data genres that will populate the **StoreIndexViewModel**.</span></span>
    > 
    > <span data-ttu-id="abdb3-453">建立及設定後**StoreIndexViewModel**物件，它會做為引數傳遞給**檢視**方法。</span><span class="sxs-lookup"><span data-stu-id="abdb3-453">After creating and setting up the **StoreIndexViewModel** object, it will be passed as an argument to the **View** method.</span></span> <span data-ttu-id="abdb3-454">這表示檢視範本將會產生 HTML 回應與它使用該物件。</span><span class="sxs-lookup"><span data-stu-id="abdb3-454">This indicates that the View template will use that object to generate an HTML response with it.</span></span>
4. <span data-ttu-id="abdb3-455">取代**索引**方法取代下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="abdb3-455">Replace the **Index** method with the following code:</span></span>

    <span data-ttu-id="abdb3-456">(程式碼片段- *ASP.NET MVC 4 基礎 Ex5 StoreController 索引方法*)</span><span class="sxs-lookup"><span data-stu-id="abdb3-456">(Code Snippet - *ASP.NET MVC 4 Fundamentals - Ex5 StoreController Index method*)</span></span>


    [!code-csharp[Main](aspnet-mvc-4-fundamentals/samples/sample13.cs)]

    > [!NOTE]
    > <span data-ttu-id="abdb3-457">如果您熟悉 C#，您可能會假設也使用**var**表示**viewModel**變數是晚期繫結。</span><span class="sxs-lookup"><span data-stu-id="abdb3-457">If you're unfamiliar with C#, you may assume that using **var** means that the **viewModel** variable is late-bound.</span></span> <span data-ttu-id="abdb3-458">不正確-C# 編譯器使用根據指派給變數的類型推斷來判斷， **viewModel**的型別**StoreIndexViewModel**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-458">That's not correct - the C# compiler is using type-inference based on what you assign to the variable to determine that **viewModel** is of type **StoreIndexViewModel**.</span></span> <span data-ttu-id="abdb3-459">此外，藉由編譯本機**viewModel**變數作為**StoreIndexViewModel** get 編譯時期檢查和 Visual Studio 程式碼編輯器支援類型。</span><span class="sxs-lookup"><span data-stu-id="abdb3-459">Also, by compiling the local **viewModel** variable as a **StoreIndexViewModel** type you get compile-time checking and Visual Studio code-editor support.</span></span>

<a id="Ex5Task4"></a>

<a id="Task_4_-_Creating_a_View_Template_that_Uses_StoreIndexViewModel"></a>
#### <a name="task-4---creating-a-view-template-that-uses-storeindexviewmodel"></a><span data-ttu-id="abdb3-460">工作 4-建立使用 StoreIndexViewModel 檢視範本</span><span class="sxs-lookup"><span data-stu-id="abdb3-460">Task 4 - Creating a View Template that Uses StoreIndexViewModel</span></span>

<span data-ttu-id="abdb3-461">在這項工作，您將建立的檢視範本，將使用傳遞從控制器 StoreIndexViewModel 物件顯示的內容類型清單。</span><span class="sxs-lookup"><span data-stu-id="abdb3-461">In this task, you will create a View template that will use a StoreIndexViewModel object passed from the Controller to display a list of genres.</span></span>

1. <span data-ttu-id="abdb3-462">之前建立新的檢視表範本，讓我們來建置專案，讓**新增檢視對話方塊**知道**StoreIndexViewModel**類別。</span><span class="sxs-lookup"><span data-stu-id="abdb3-462">Before creating the new View template, let's build the project so that the **Add View Dialog** knows about the **StoreIndexViewModel** class.</span></span> <span data-ttu-id="abdb3-463">建置專案時選取**建置**功能表項目，然後**建置 MvcMusicStore**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-463">Build the project by selecting the **Build** menu item and then **Build MvcMusicStore**.</span></span>

    <span data-ttu-id="abdb3-464">![建置專案](aspnet-mvc-4-fundamentals/_static/image22.png "建置專案")</span><span class="sxs-lookup"><span data-stu-id="abdb3-464">![Building the project](aspnet-mvc-4-fundamentals/_static/image22.png "Building the project")</span></span>

    <span data-ttu-id="abdb3-465">*建置專案*</span><span class="sxs-lookup"><span data-stu-id="abdb3-465">*Building the project*</span></span>
2. <span data-ttu-id="abdb3-466">建立新的檢視範本。</span><span class="sxs-lookup"><span data-stu-id="abdb3-466">Create a new View template.</span></span> <span data-ttu-id="abdb3-467">若要這樣做，請以滑鼠右鍵按一下**索引**方法，然後選取**加入檢視**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-467">To do that, right-click inside the **Index** method and select **Add View**.</span></span>

    <span data-ttu-id="abdb3-468">![加入檢視](aspnet-mvc-4-fundamentals/_static/image23.png "加入的檢視")</span><span class="sxs-lookup"><span data-stu-id="abdb3-468">![Adding a View](aspnet-mvc-4-fundamentals/_static/image23.png "Adding a View")</span></span>

    <span data-ttu-id="abdb3-469">*加入的檢視*</span><span class="sxs-lookup"><span data-stu-id="abdb3-469">*Adding a View*</span></span>
3. <span data-ttu-id="abdb3-470">因為**新增檢視對話方塊**已經叫用**StoreController**，它會將檢視範本預設會在新增**\Views\Store\Index.cshtml**檔案。</span><span class="sxs-lookup"><span data-stu-id="abdb3-470">Because the **Add View Dialog** was invoked from the **StoreController**, it will add the View template by default in a **\Views\Store\Index.cshtml** file.</span></span> <span data-ttu-id="abdb3-471">請檢查**建立強型別-檢視**核取方塊，然後選取  **StoreIndexViewModel**為**模型類別**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-471">Check the **Create a strongly-typed-view** checkbox and then select **StoreIndexViewModel** as the **Model class**.</span></span> <span data-ttu-id="abdb3-472">此外，請確定選取的檢視引擎是**Razor**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-472">Also, make sure that the View engine selected is **Razor**.</span></span> <span data-ttu-id="abdb3-473">按一下 [加入] 。</span><span class="sxs-lookup"><span data-stu-id="abdb3-473">Click **Add**.</span></span>

    <span data-ttu-id="abdb3-474">![新增檢視對話方塊](aspnet-mvc-4-fundamentals/_static/image24.png "新增檢視對話方塊")</span><span class="sxs-lookup"><span data-stu-id="abdb3-474">![Add View Dialog](aspnet-mvc-4-fundamentals/_static/image24.png "Add View Dialog")</span></span>

    <span data-ttu-id="abdb3-475">*新增檢視對話方塊*</span><span class="sxs-lookup"><span data-stu-id="abdb3-475">*Add View Dialog*</span></span>

    <span data-ttu-id="abdb3-476">**\Views\Store\Index.cshtml**建立並開啟檢視範本檔案。</span><span class="sxs-lookup"><span data-stu-id="abdb3-476">The **\Views\Store\Index.cshtml** View template file is created and opened.</span></span> <span data-ttu-id="abdb3-477">根據提供的資訊**加入檢視**對話方塊在最後一個步驟中，範本就會預期收到檢視**StoreIndexViewModel**做為要用來產生 HTML 回應資料的執行個體。</span><span class="sxs-lookup"><span data-stu-id="abdb3-477">Based on the information provided to the **Add View** dialog in the last step, the View template will expect a **StoreIndexViewModel** instance as the data to use to generate an HTML response.</span></span> <span data-ttu-id="abdb3-478">您會注意到範本會繼承`ViewPage<musicstore.viewmodels.storeindexviewmodel>`C# 中。</span><span class="sxs-lookup"><span data-stu-id="abdb3-478">You will notice that the template inherits a `ViewPage<musicstore.viewmodels.storeindexviewmodel>` in C#.</span></span>

<a id="Ex5Task5"></a>

<a id="Task_5_-_Updating_the_View_Template"></a>
#### <a name="task-5---updating-the-view-template"></a><span data-ttu-id="abdb3-479">工作 5-正在更新檢視範本</span><span class="sxs-lookup"><span data-stu-id="abdb3-479">Task 5 - Updating the View Template</span></span>

<span data-ttu-id="abdb3-480">在這項工作，您將會更新擷取的內容類型和其頁面中的名稱數目的最後一個工作中建立的檢視範本。</span><span class="sxs-lookup"><span data-stu-id="abdb3-480">In this task, you will update the View template created in the last task to retrieve the number of genres and their names within the page.</span></span>

> [!NOTE]
> <span data-ttu-id="abdb3-481">您將使用語法 @ (通常稱為&quot;程式碼區塊&quot;) 來執行程式碼內檢視範本。</span><span class="sxs-lookup"><span data-stu-id="abdb3-481">You will use @ syntax (often referred to as &quot;code nuggets&quot;) to execute code within the View template.</span></span>


1. <span data-ttu-id="abdb3-482">在**Index.cshtml**檔案內**存放區**資料夾中，其程式碼替換成下列：</span><span class="sxs-lookup"><span data-stu-id="abdb3-482">In the **Index.cshtml** file, within the **Store** folder, replace its code with the following:</span></span>


    [!code-cshtml[Main](aspnet-mvc-4-fundamentals/samples/sample14.cshtml)]

    > [!NOTE]
    > <span data-ttu-id="abdb3-483">一旦您完成輸入超過此時限後字**模型**，Visual Studio Intellisense 會顯示一份可能的內容的方法可供選擇。</span><span class="sxs-lookup"><span data-stu-id="abdb3-483">As soon as you finish typing the period after the word **Model**, Visual Studio's Intellisense will show a list of possible properties and methods to choose from.</span></span>
    > 
    > ![](aspnet-mvc-4-fundamentals/_static/image25.png)
    > 
    > <span data-ttu-id="abdb3-484">*取得模型屬性和方法的 Visual Studio IntelliSense*</span><span class="sxs-lookup"><span data-stu-id="abdb3-484">*Getting Model properties and methods with Visual Studio's IntelliSense*</span></span>
    > 
    > <span data-ttu-id="abdb3-485">**模型**屬性參考**StoreIndexViewModel**控制器傳遞至檢視表範本的物件。</span><span class="sxs-lookup"><span data-stu-id="abdb3-485">The **Model** property references the **StoreIndexViewModel** object that the Controller passed to the View template.</span></span> <span data-ttu-id="abdb3-486">這表示您可以存取的所有資料從控制器傳遞至檢視表範本，透過**模型**屬性，並將其格式化成適當的 HTML 回應中檢視範本。</span><span class="sxs-lookup"><span data-stu-id="abdb3-486">This means that you can access all of the data passed from the Controller to the View template via the **Model** property, and format it into an appropriate HTML response within the View template.</span></span>
    > 
    > <span data-ttu-id="abdb3-487">您可以選取**NumberOfGenres**屬性從 Intellisense 清單而不是輸入中，然後它會自動完成它按**tab 鍵**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-487">You can just select the **NumberOfGenres** property from the Intellisense list rather than typing it in and then it will auto-complete it by pressing the **tab key**.</span></span>
2. <span data-ttu-id="abdb3-488">透過內容類型清單中的迴圈**StoreIndexViewModel**並建立 HTML  **&lt;ul&gt;** 清單使用**foreach**迴圈。</span><span class="sxs-lookup"><span data-stu-id="abdb3-488">Loop over the genre list in **StoreIndexViewModel** and create an HTML **&lt;ul&gt;** list using a **foreach** loop.</span></span>
<span data-ttu-id="abdb3-489">(C#)</span><span class="sxs-lookup"><span data-stu-id="abdb3-489">(C#)</span></span>

    [!code-cshtml[Main](aspnet-mvc-4-fundamentals/samples/sample15.cshtml)]
3. <span data-ttu-id="abdb3-490">按**F5**執行應用程式，然後瀏覽**/儲存**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-490">Press **F5** to run the Application and browse **/Store**.</span></span> <span data-ttu-id="abdb3-491">您會看到傳入的內容類型清單**StoreIndexViewModel**物件從**StoreController**檢視範本。</span><span class="sxs-lookup"><span data-stu-id="abdb3-491">You will see the list of genres passed in the **StoreIndexViewModel** object from the **StoreController** to the View template.</span></span>

    <span data-ttu-id="abdb3-492">![檢視顯示的內容類型清單](aspnet-mvc-4-fundamentals/_static/image26.png "檢視顯示的內容類型清單")</span><span class="sxs-lookup"><span data-stu-id="abdb3-492">![View displaying a list of genres](aspnet-mvc-4-fundamentals/_static/image26.png "View displaying a list of genres")</span></span>

    <span data-ttu-id="abdb3-493">*檢視顯示的內容類型清單*</span><span class="sxs-lookup"><span data-stu-id="abdb3-493">*View displaying a list of genres*</span></span>
4. <span data-ttu-id="abdb3-494">關閉瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="abdb3-494">Close the browser.</span></span>

<a id="Exercise6"></a>

<a id="Exercise_6_Using_Parameters_in_View"></a>
### <a name="exercise-6-using-parameters-in-view"></a><span data-ttu-id="abdb3-495">練習 6： 在檢視中使用參數</span><span class="sxs-lookup"><span data-stu-id="abdb3-495">Exercise 6: Using Parameters in View</span></span>

<span data-ttu-id="abdb3-496">練習 3 中，您學會如何將參數傳遞至控制器。</span><span class="sxs-lookup"><span data-stu-id="abdb3-496">In Exercise 3 you learned how to pass parameters to the Controller.</span></span> <span data-ttu-id="abdb3-497">在此練習中，您將學習如何在檢視表範本中使用這些參數。</span><span class="sxs-lookup"><span data-stu-id="abdb3-497">In this exercise, you will learn how to use those parameters in the View template.</span></span> <span data-ttu-id="abdb3-498">基於這個目的，您將介紹第一次將協助您管理您的資料和網域邏輯的模型類別。</span><span class="sxs-lookup"><span data-stu-id="abdb3-498">For that purpose, you will be introduced first to Model classes that will help you to manage your data and domain logic.</span></span> <span data-ttu-id="abdb3-499">此外，您將學習如何建立無須擔心之類的編碼方式的 URL 路徑的 ASP.NET MVC 應用程式內的網頁的連結。</span><span class="sxs-lookup"><span data-stu-id="abdb3-499">Additionally, you will learn how to create links to pages inside the ASP.NET MVC application without worrying of things like URL paths encoding.</span></span>

<a id="Ex6Task1"></a>

<a id="Task_1_-_Adding_Model_Classes"></a>
#### <a name="task-1---adding-model-classes"></a><span data-ttu-id="abdb3-500">工作 1-新增模型類別</span><span class="sxs-lookup"><span data-stu-id="abdb3-500">Task 1 - Adding Model Classes</span></span>

<span data-ttu-id="abdb3-501">不同於 ViewModels，也就建立只是為了從控制器的資訊傳遞至檢視模型類別會建置包含和管理資料和網域邏輯。</span><span class="sxs-lookup"><span data-stu-id="abdb3-501">Unlike ViewModels, which are created just to pass information from the Controller to the View, Model classes are built to contain and manage data and domain logic.</span></span> <span data-ttu-id="abdb3-502">在這項工作中，您會將兩個模型類別來代表這些概念：**類型**和**專輯**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-502">In this task you will add two model classes to represent these concepts: **Genre** and **Album**.</span></span>

1. <span data-ttu-id="abdb3-503">如果尚未開啟，啟動**VS Express for Web**</span><span class="sxs-lookup"><span data-stu-id="abdb3-503">If not already open, start **VS Express for Web**</span></span>
2. <span data-ttu-id="abdb3-504">在**檔案**功能表上，選擇**開啟專案**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-504">In the **File** menu, choose **Open Project**.</span></span> <span data-ttu-id="abdb3-505">在 [開啟專案] 對話方塊中，瀏覽至**Source\Ex06 UsingParametersInView\Begin**，選取**Begin.sln**按一下**開啟**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-505">In the Open Project dialog, browse to **Source\Ex06-UsingParametersInView\Begin**, select **Begin.sln** and click **Open**.</span></span> <span data-ttu-id="abdb3-506">或者，您可以繼續使用此方案完成上一個練習之後取得。</span><span class="sxs-lookup"><span data-stu-id="abdb3-506">Alternatively, you may continue with the solution that you obtained after completing the previous exercise.</span></span>

    1. <span data-ttu-id="abdb3-507">如果您開啟提供**開始**方案，您必須下載某些遺漏的 NuGet 套件才能繼續。</span><span class="sxs-lookup"><span data-stu-id="abdb3-507">If you opened the provided **Begin** solution, you will need to download some missing NuGet packages before continue.</span></span> <span data-ttu-id="abdb3-508">若要這樣做，請按一下**專案**功能表，然後選取**管理 NuGet 封裝**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-508">To do this, click the **Project** menu and select **Manage NuGet Packages**.</span></span>
    2. <span data-ttu-id="abdb3-509">在**管理 NuGet 封裝**] 對話方塊中，按一下 [**還原**才能下載遺漏的封裝。</span><span class="sxs-lookup"><span data-stu-id="abdb3-509">In the **Manage NuGet Packages** dialog, click **Restore** in order to download missing packages.</span></span>
    3. <span data-ttu-id="abdb3-510">最後，按一下 建置方案**建置** | **建置方案**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-510">Finally, build the solution by clicking **Build** | **Build Solution**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="abdb3-511">使用 NuGet 的優點之一是您不需要在專案中，所有的程式庫的出貨減少專案大小。</span><span class="sxs-lookup"><span data-stu-id="abdb3-511">One of the advantages of using NuGet is that you don't have to ship all the libraries in your project, reducing the project size.</span></span> <span data-ttu-id="abdb3-512">NuGet 的強大工具，請藉由指定封裝版本在 Packages.config 檔案中，您將會成功下載所有必要的程式庫第一次您執行專案。</span><span class="sxs-lookup"><span data-stu-id="abdb3-512">With NuGet Power Tools, by specifying the package versions in the Packages.config file, you will be able to download all the required libraries the first time you run the project.</span></span> <span data-ttu-id="abdb3-513">這就是為什麼您必須從這個實驗室中開啟現有的方案後執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="abdb3-513">This is why you will have to run these steps after you open an existing solution from this lab.</span></span>
3. <span data-ttu-id="abdb3-514">新增**類型**模型類別。</span><span class="sxs-lookup"><span data-stu-id="abdb3-514">Add a **Genre** Model class.</span></span> <span data-ttu-id="abdb3-515">若要這樣做，請以滑鼠右鍵按一下**模型**資料夾中的**方案總管 中**，選取**新增**然後**新項目**選項。</span><span class="sxs-lookup"><span data-stu-id="abdb3-515">To do this, right-click the **Models** folder in the **Solution Explorer**, select **Add** and then the **New Item** option.</span></span> <span data-ttu-id="abdb3-516">在下**程式碼**，選擇**類別**項目，並將檔案命名*Genre.cs*，然後按一下 **新增**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-516">Under **Code**, choose the **Class** item and name the file *Genre.cs*, then click **Add**.</span></span>

    <span data-ttu-id="abdb3-517">![將類別加入](aspnet-mvc-4-fundamentals/_static/image27.png "加入類別")</span><span class="sxs-lookup"><span data-stu-id="abdb3-517">![Adding a class](aspnet-mvc-4-fundamentals/_static/image27.png "Adding a class")</span></span>

    <span data-ttu-id="abdb3-518">*加入新項目*</span><span class="sxs-lookup"><span data-stu-id="abdb3-518">*Adding a new item*</span></span>

    <span data-ttu-id="abdb3-519">![新增內容類型的模型類別](aspnet-mvc-4-fundamentals/_static/image28.png "新增內容類型的模型類別")</span><span class="sxs-lookup"><span data-stu-id="abdb3-519">![Add Genre Model Class](aspnet-mvc-4-fundamentals/_static/image28.png "Add Genre Model Class")</span></span>

    <span data-ttu-id="abdb3-520">*新增內容類型的模型類別*</span><span class="sxs-lookup"><span data-stu-id="abdb3-520">*Add Genre Model Class*</span></span>
4. <span data-ttu-id="abdb3-521">新增**名稱**類型類別的屬性。</span><span class="sxs-lookup"><span data-stu-id="abdb3-521">Add a **Name** property to the Genre class.</span></span> <span data-ttu-id="abdb3-522">若要這樣做，請加入下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="abdb3-522">To do this, add the following code:</span></span>

    <span data-ttu-id="abdb3-523">(程式碼片段- *ASP.NET MVC 4 基本概念 Ex6 類型*)</span><span class="sxs-lookup"><span data-stu-id="abdb3-523">(Code Snippet - *ASP.NET MVC 4 Fundamentals - Ex6 Genre*)</span></span>


    [!code-csharp[Main](aspnet-mvc-4-fundamentals/samples/sample16.cs)]
5. <span data-ttu-id="abdb3-524">相同的程序之前，新增**專輯**類別。</span><span class="sxs-lookup"><span data-stu-id="abdb3-524">Following the same procedure as before, add an **Album** class.</span></span> <span data-ttu-id="abdb3-525">若要這樣做，請以滑鼠右鍵按一下**模型**資料夾中的**方案總管 中**，選取**新增**然後**新項目**選項。</span><span class="sxs-lookup"><span data-stu-id="abdb3-525">To do this, right-click the **Models** folder in the **Solution Explorer**, select **Add** and then the **New Item** option.</span></span> <span data-ttu-id="abdb3-526">在下**程式碼**，選擇**類別**項目，並將檔案命名*Album.cs*，然後按一下 **新增**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-526">Under **Code**, choose the **Class** item and name the file *Album.cs*, then click **Add**.</span></span>
6. <span data-ttu-id="abdb3-527">專輯類別中加入兩個屬性：**類型**和**標題**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-527">Add two properties to the Album class: **Genre** and **Title**.</span></span> <span data-ttu-id="abdb3-528">若要這樣做，請加入下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="abdb3-528">To do this, add the following code:</span></span>

    <span data-ttu-id="abdb3-529">(程式碼片段- *ASP.NET MVC 4 基本概念 Ex6 專輯*)</span><span class="sxs-lookup"><span data-stu-id="abdb3-529">(Code Snippet - *ASP.NET MVC 4 Fundamentals - Ex6 Album*)</span></span>


    [!code-csharp[Main](aspnet-mvc-4-fundamentals/samples/sample17.cs)]

<a id="Ex6Task2"></a>

<a id="Task_2_-_Adding_a_StoreBrowseViewModel"></a>
#### <a name="task-2---adding-a-storebrowseviewmodel"></a><span data-ttu-id="abdb3-530">工作 2-新增 StoreBrowseViewModel</span><span class="sxs-lookup"><span data-stu-id="abdb3-530">Task 2 - Adding a StoreBrowseViewModel</span></span>

<span data-ttu-id="abdb3-531">A **StoreBrowseViewModel**將這項工作中用來顯示符合所選的類型的相簿。</span><span class="sxs-lookup"><span data-stu-id="abdb3-531">A **StoreBrowseViewModel** will be used in this task to show the Albums that match a selected Genre.</span></span> <span data-ttu-id="abdb3-532">在這項工作，您會建立這個類別，並新增兩個屬性，以處理**類型**及其**專輯**的清單。</span><span class="sxs-lookup"><span data-stu-id="abdb3-532">In this task, you will create this class and then add two properties to handle the **Genre** and its **Album**'s List.</span></span>

1. <span data-ttu-id="abdb3-533">新增**StoreBrowseViewModel**類別。</span><span class="sxs-lookup"><span data-stu-id="abdb3-533">Add a **StoreBrowseViewModel** class.</span></span> <span data-ttu-id="abdb3-534">若要這樣做，請以滑鼠右鍵按一下**ViewModels**資料夾中的**方案總管 中**，選取**新增**然後**新項目**選項。</span><span class="sxs-lookup"><span data-stu-id="abdb3-534">To do this, right-click the **ViewModels** folder in the **Solution Explorer**, select **Add** and then the **New Item** option.</span></span> <span data-ttu-id="abdb3-535">在下**程式碼**，選擇**類別**項目，並將檔案命名*StoreBrowseViewModel.cs*，然後按一下 **新增**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-535">Under **Code**, choose the **Class** item and name the file *StoreBrowseViewModel.cs*, then click **Add**.</span></span>
2. <span data-ttu-id="abdb3-536">將參考加入至模型中**StoreBrowseViewModel**類別。</span><span class="sxs-lookup"><span data-stu-id="abdb3-536">Add a reference to the Models in **StoreBrowseViewModel** class.</span></span> <span data-ttu-id="abdb3-537">若要這樣做，請加入下列使用命名空間：</span><span class="sxs-lookup"><span data-stu-id="abdb3-537">To do this, add the following using namespace:</span></span>

    <span data-ttu-id="abdb3-538">(程式碼片段- *ASP.NET MVC 4 基本概念 Ex6 UsingModel*)</span><span class="sxs-lookup"><span data-stu-id="abdb3-538">(Code Snippet - *ASP.NET MVC 4 Fundamentals - Ex6 UsingModel*)</span></span>


    [!code-csharp[Main](aspnet-mvc-4-fundamentals/samples/sample18.cs)]
3. <span data-ttu-id="abdb3-539">加入兩個屬性，以**StoreBrowseViewModel**類別：**類型**和**專輯**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-539">Add two properties to **StoreBrowseViewModel** class: **Genre** and **Albums**.</span></span> <span data-ttu-id="abdb3-540">若要這樣做，請加入下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="abdb3-540">To do this, add the following code:</span></span>

    <span data-ttu-id="abdb3-541">(程式碼片段- *ASP.NET MVC 4 基本概念 Ex6 ModelProperties*)</span><span class="sxs-lookup"><span data-stu-id="abdb3-541">(Code Snippet - *ASP.NET MVC 4 Fundamentals - Ex6 ModelProperties*)</span></span>


    [!code-csharp[Main](aspnet-mvc-4-fundamentals/samples/sample19.cs)]

    > [!NOTE]
    > <span data-ttu-id="abdb3-542">什麼是**清單&lt;專輯&gt;** ？: 使用此定義**清單&lt;T&gt;** 型別，其中**T**限制這項目型別**清單**屬於，在此情況下**專輯**（或其任何子代）。</span><span class="sxs-lookup"><span data-stu-id="abdb3-542">What is **List&lt;Album&gt;** ?: This definition is using the **List&lt;T&gt;** type, where **T** constrains the type to which elements of this **List** belong to, in this case **Album** (or any of its descendants).</span></span>
    > 
    > <span data-ttu-id="abdb3-543">這項功能來設計類別和類別或方法宣告並具現化用戶端程式碼是 C# 語言的功能之前，延後的一或多個型別規格的方法呼叫**泛型**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-543">This ability to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code is a feature of the C# language called **Generics**.</span></span>
    > 
    > <span data-ttu-id="abdb3-544">**清單&lt;T&gt;** 相當於泛型**ArrayList**輸入，並可用於**System.Collections.Generic**命名空間。</span><span class="sxs-lookup"><span data-stu-id="abdb3-544">**List&lt;T&gt;** is the generic equivalent of the **ArrayList** type and is available in the **System.Collections.Generic** namespace.</span></span> <span data-ttu-id="abdb3-545">使用的優點的其中一個**泛型**是，因為指定的類型，您不需要處理的型別檢查作業，例如轉型成項目**專輯**像您一樣**ArrayList**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-545">One of the benefits of using **generics** is that since the type is specified, you do not need to take care of type checking operations such as casting the elements into **Album** as you would do with an **ArrayList**.</span></span>

<a id="Ex6Task3"></a>

<a id="Task_3_-_Using_the_New_ViewModel_in_the_StoreController"></a>
#### <a name="task-3---using-the-new-viewmodel-in-the-storecontroller"></a><span data-ttu-id="abdb3-546">工作 3-使用新 ViewModel StoreController 中</span><span class="sxs-lookup"><span data-stu-id="abdb3-546">Task 3 - Using the New ViewModel in the StoreController</span></span>

<span data-ttu-id="abdb3-547">在這個工作中，您將修改**StoreController**的**瀏覽**和**詳細資料**動作方法，以使用新**StoreBrowseViewModel**.</span><span class="sxs-lookup"><span data-stu-id="abdb3-547">In this task, you will modify the **StoreController**'s **Browse** and **Details** action methods to use the new **StoreBrowseViewModel**.</span></span>

1. <span data-ttu-id="abdb3-548">將參考加入至 [模型] 資料夾中**StoreController**類別。</span><span class="sxs-lookup"><span data-stu-id="abdb3-548">Add a reference to the Models folder in **StoreController** class.</span></span> <span data-ttu-id="abdb3-549">若要這樣做，請展開**控制器**資料夾中的**方案總管 中**並開啟**StoreController**類別。</span><span class="sxs-lookup"><span data-stu-id="abdb3-549">To do this, expand the **Controllers** folder in the **Solution Explorer** and open the **StoreController** class.</span></span> <span data-ttu-id="abdb3-550">然後加入下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="abdb3-550">Then add the following code:</span></span>

    <span data-ttu-id="abdb3-551">(程式碼片段- *ASP.NET MVC 4 基本概念 Ex6 UsingModelInController*)</span><span class="sxs-lookup"><span data-stu-id="abdb3-551">(Code Snippet - *ASP.NET MVC 4 Fundamentals - Ex6 UsingModelInController*)</span></span>


    [!code-csharp[Main](aspnet-mvc-4-fundamentals/samples/sample20.cs)]
2. <span data-ttu-id="abdb3-552">取代**瀏覽**動作方法，以使用**StoreViewBrowseController**類別。</span><span class="sxs-lookup"><span data-stu-id="abdb3-552">Replace the **Browse** action method to use the **StoreViewBrowseController** class.</span></span> <span data-ttu-id="abdb3-553">您將使用虛擬資料建立內容類型和兩個新的專輯物件 （在下一步的實際操作實驗室中您會使用資料庫的實際資料）。</span><span class="sxs-lookup"><span data-stu-id="abdb3-553">You will create a Genre and two new Albums objects with dummy data (in the next Hands-on Lab you will consume real data from a database).</span></span> <span data-ttu-id="abdb3-554">若要這樣做，請取代**瀏覽**方法取代下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="abdb3-554">To do this, replace the **Browse** method with the following code:</span></span>

    <span data-ttu-id="abdb3-555">(程式碼片段- *ASP.NET MVC 4 基本概念 Ex6 BrowseMethod*)</span><span class="sxs-lookup"><span data-stu-id="abdb3-555">(Code Snippet - *ASP.NET MVC 4 Fundamentals - Ex6 BrowseMethod*)</span></span>


    [!code-csharp[Main](aspnet-mvc-4-fundamentals/samples/sample21.cs)]
3. <span data-ttu-id="abdb3-556">取代**詳細資料**動作方法，以使用**StoreViewBrowseController**類別。</span><span class="sxs-lookup"><span data-stu-id="abdb3-556">Replace the **Details** action method to use the **StoreViewBrowseController** class.</span></span> <span data-ttu-id="abdb3-557">您將建立新**專輯**物件傳回至**檢視**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-557">You will create a new **Album** object to be returned to the **View**.</span></span> <span data-ttu-id="abdb3-558">若要這樣做，請取代**詳細資料**方法取代下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="abdb3-558">To do this, replace the **Details** method with the following code:</span></span>

    <span data-ttu-id="abdb3-559">(程式碼片段- *ASP.NET MVC 4 基本概念 Ex6 DetailsMethod*)</span><span class="sxs-lookup"><span data-stu-id="abdb3-559">(Code Snippet - *ASP.NET MVC 4 Fundamentals - Ex6 DetailsMethod*)</span></span>


    [!code-csharp[Main](aspnet-mvc-4-fundamentals/samples/sample22.cs)]

<a id="Ex6Task4"></a>

<a id="Task_4_-_Adding_a_Browse_View_Template"></a>
#### <a name="task-4---adding-a-browse-view-template"></a><span data-ttu-id="abdb3-560">工作 4-新增瀏覽檢視範本</span><span class="sxs-lookup"><span data-stu-id="abdb3-560">Task 4 - Adding a Browse View Template</span></span>

<span data-ttu-id="abdb3-561">在這個工作中，您將加入**瀏覽**檢視，以顯示找到的特定內容類型的相簿。</span><span class="sxs-lookup"><span data-stu-id="abdb3-561">In this task, you will add a **Browse** View to show the Albums found for a specific Genre.</span></span>

1. <span data-ttu-id="abdb3-562">之前建立新的檢視表範本，您應該可以建置專案，讓**加入檢視**對話方塊知道**ViewModel**類別，才能使用。</span><span class="sxs-lookup"><span data-stu-id="abdb3-562">Before creating the new View template, you should build the project so that the **Add View** Dialog knows about the **ViewModel** class to use.</span></span> <span data-ttu-id="abdb3-563">建置專案時選取**建置**功能表項目，然後**建置 MvcMusicStore**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-563">Build the project by selecting the **Build** menu item and then **Build MvcMusicStore**.</span></span>
2. <span data-ttu-id="abdb3-564">新增**瀏覽**檢視。</span><span class="sxs-lookup"><span data-stu-id="abdb3-564">Add a **Browse** View.</span></span> <span data-ttu-id="abdb3-565">若要這樣做，以滑鼠右鍵按一下**瀏覽**動作方法的**StoreController**按一下**加入檢視**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-565">To do this, right-click in the **Browse** action method of the **StoreController** and click **Add View**.</span></span>
3. <span data-ttu-id="abdb3-566">在**加入檢視**對話方塊方塊中，確認檢視名稱**瀏覽**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-566">In the **Add View** dialog box, verify that the View Name is **Browse**.</span></span> <span data-ttu-id="abdb3-567">請檢查**建立強型別檢視**核取方塊並選取**StoreBrowseViewModel**從**模型類別**下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="abdb3-567">Check the **Create a strongly-typed view** checkbox and select **StoreBrowseViewModel** from the **Model class** dropdown.</span></span> <span data-ttu-id="abdb3-568">將其他欄位的預設值。</span><span class="sxs-lookup"><span data-stu-id="abdb3-568">Leave the other fields with their default value.</span></span> <span data-ttu-id="abdb3-569">然後按一下 [加入] 。</span><span class="sxs-lookup"><span data-stu-id="abdb3-569">Then click **Add**.</span></span>

    <span data-ttu-id="abdb3-570">![加入瀏覽檢視](aspnet-mvc-4-fundamentals/_static/image29.png "加入瀏覽 檢視")</span><span class="sxs-lookup"><span data-stu-id="abdb3-570">![Adding a Browse View](aspnet-mvc-4-fundamentals/_static/image29.png "Adding a Browse View")</span></span>

    <span data-ttu-id="abdb3-571">*加入瀏覽 檢視*</span><span class="sxs-lookup"><span data-stu-id="abdb3-571">*Adding a Browse View*</span></span>
4. <span data-ttu-id="abdb3-572">修改**Browse.cshtml**來顯示內容類型的資訊，存取**StoreBrowseViewModel**傳遞至檢視表範本的物件。</span><span class="sxs-lookup"><span data-stu-id="abdb3-572">Modify the **Browse.cshtml** to display the Genre's information, accessing the **StoreBrowseViewModel** object that is passed to the view template.</span></span> <span data-ttu-id="abdb3-573">若要這樣做，取代為下列內容: (C#)</span><span class="sxs-lookup"><span data-stu-id="abdb3-573">To do this, replace the content with the following: (C#)</span></span>

    [!code-cshtml[Main](aspnet-mvc-4-fundamentals/samples/sample23.cshtml)]

<a id="Ex6Task5"></a>

<a id="Task_5_-_Running_the_Application"></a>
#### <a name="task-5---running-the-application"></a><span data-ttu-id="abdb3-574">工作 5-執行應用程式</span><span class="sxs-lookup"><span data-stu-id="abdb3-574">Task 5 - Running the Application</span></span>

<span data-ttu-id="abdb3-575">在這個工作中，您將測試的**瀏覽**方法會擷取從相簿**瀏覽**方法動作。</span><span class="sxs-lookup"><span data-stu-id="abdb3-575">In this task, you will test that the **Browse** method retrieves Albums from the **Browse** method action.</span></span>

1. <span data-ttu-id="abdb3-576">按**F5**執行應用程式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-576">Press **F5** to run the Application.</span></span>
2. <span data-ttu-id="abdb3-577">在首頁上，啟動專案。</span><span class="sxs-lookup"><span data-stu-id="abdb3-577">The project starts in the Home page.</span></span> <span data-ttu-id="abdb3-578">將 URL 變更為  **/儲存] / [瀏覽？內容類型 = Disco**以確認動作傳回兩個相簿。</span><span class="sxs-lookup"><span data-stu-id="abdb3-578">Change the URL to **/Store/Browse?Genre=Disco** to verify that the action returns two Albums.</span></span>

    <span data-ttu-id="abdb3-579">![瀏覽市集 Disco 專輯](aspnet-mvc-4-fundamentals/_static/image30.png "瀏覽市集 Disco 相簿")</span><span class="sxs-lookup"><span data-stu-id="abdb3-579">![Browsing Store Disco Albums](aspnet-mvc-4-fundamentals/_static/image30.png "Browsing Store Disco Albums")</span></span>

    <span data-ttu-id="abdb3-580">*瀏覽市集 Disco 相簿*</span><span class="sxs-lookup"><span data-stu-id="abdb3-580">*Browsing Store Disco Albums*</span></span>

<a id="Ex6Task6"></a>

<a id="Task_6_-_Displaying_information_About_a_Specific_Album"></a>
#### <a name="task-6---displaying-information-about-a-specific-album"></a><span data-ttu-id="abdb3-581">工作 6-顯示資訊的相關特定專輯</span><span class="sxs-lookup"><span data-stu-id="abdb3-581">Task 6 - Displaying information About a Specific Album</span></span>

<span data-ttu-id="abdb3-582">在這個工作中，您將實作**存放區/詳細資料**檢視來顯示特定專輯的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="abdb3-582">In this task, you will implement the **Store/Details** view to display information about a specific album.</span></span> <span data-ttu-id="abdb3-583">在這個實際操作實驗室中，您將會顯示關於專輯的所有項目已經包含在**檢視**範本。</span><span class="sxs-lookup"><span data-stu-id="abdb3-583">In this Hands-on Lab, everything you will display about the album is already contained in the **View** template.</span></span> <span data-ttu-id="abdb3-584">是的而不是建立**StoreDetailsViewModel**類別，您將使用目前**StoreBrowseViewModel**傳遞給它來專輯的範本。</span><span class="sxs-lookup"><span data-stu-id="abdb3-584">So, instead of creating a **StoreDetailsViewModel** class, you will use the current **StoreBrowseViewModel** template passing the Album to it.</span></span>

1. <span data-ttu-id="abdb3-585">關閉瀏覽器，如有需要若要返回 Visual Studio 視窗。</span><span class="sxs-lookup"><span data-stu-id="abdb3-585">Close the browser if needed, to return to the Visual Studio window.</span></span> <span data-ttu-id="abdb3-586">加入新**詳細資料**檢視**StoreController**的**詳細資料**動作方法。</span><span class="sxs-lookup"><span data-stu-id="abdb3-586">Add a new **Details** view for the **StoreController**'s **Details** action method.</span></span> <span data-ttu-id="abdb3-587">若要這樣做，請以滑鼠右鍵按一下**詳細資料**方法中的**StoreController**類別，並按一下**加入檢視**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-587">To do this, right-click the **Details** method in the **StoreController** class and click **Add View**.</span></span>
2. <span data-ttu-id="abdb3-588">在**加入檢視** 對話方塊中，確認**檢視名稱**是**詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-588">In the **Add View** dialog, verify that the **View Name** is **Details**.</span></span> <span data-ttu-id="abdb3-589">請檢查**建立強型別檢視**核取方塊並選取**專輯**從**模型類別**下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="abdb3-589">Check the **Create a strongly-typed view** checkbox and select **Album** from the **Model class** drop-down.</span></span> <span data-ttu-id="abdb3-590">將其他欄位的預設值。</span><span class="sxs-lookup"><span data-stu-id="abdb3-590">Leave the other fields with their default value.</span></span> <span data-ttu-id="abdb3-591">然後按一下 [加入] 。</span><span class="sxs-lookup"><span data-stu-id="abdb3-591">Then click **Add**.</span></span> <span data-ttu-id="abdb3-592">這將建立並開啟**\Views\Store\Details.cshtml**檔案。</span><span class="sxs-lookup"><span data-stu-id="abdb3-592">This will create and open a **\Views\Store\Details.cshtml** file.</span></span>

    <span data-ttu-id="abdb3-593">![加入詳細資料檢視](aspnet-mvc-4-fundamentals/_static/image31.png "加入詳細資料檢視")</span><span class="sxs-lookup"><span data-stu-id="abdb3-593">![Adding a Details View](aspnet-mvc-4-fundamentals/_static/image31.png "Adding a Details View")</span></span>

    <span data-ttu-id="abdb3-594">*加入詳細資料檢視*</span><span class="sxs-lookup"><span data-stu-id="abdb3-594">*Adding a Details View*</span></span>
3. <span data-ttu-id="abdb3-595">修改**Details.cshtml**檔案以顯示專輯資訊存取**專輯**傳遞至檢視表範本的物件。</span><span class="sxs-lookup"><span data-stu-id="abdb3-595">Modify the **Details.cshtml** file to display the Album's information, accessing the **Album** object that is passed to the view template.</span></span> <span data-ttu-id="abdb3-596">若要這樣做，取代為下列內容: (C#)</span><span class="sxs-lookup"><span data-stu-id="abdb3-596">To do this, replace the content with the following: (C#)</span></span>

    [!code-cshtml[Main](aspnet-mvc-4-fundamentals/samples/sample24.cshtml)]

<a id="Ex6Task7"></a>

<a id="Task_7_-_Running_the_Application"></a>
#### <a name="task-7---running-the-application"></a><span data-ttu-id="abdb3-597">工作 7： 執行應用程式</span><span class="sxs-lookup"><span data-stu-id="abdb3-597">Task 7 - Running the Application</span></span>

<span data-ttu-id="abdb3-598">在這個工作中，您將測試的**詳細資料**檢視擷取的專輯資訊從**詳細說明動作**方法。</span><span class="sxs-lookup"><span data-stu-id="abdb3-598">In this task, you will test that the **Details** View retrieves Album's information from the **Details action** method.</span></span>

1. <span data-ttu-id="abdb3-599">按**F5**執行應用程式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-599">Press **F5** to run the Application.</span></span>
2. <span data-ttu-id="abdb3-600">在專案開始**首頁**頁面。</span><span class="sxs-lookup"><span data-stu-id="abdb3-600">The project starts in the **Home** page.</span></span> <span data-ttu-id="abdb3-601">將 URL 變更為**/Store/Details/5**確認的專輯資訊。</span><span class="sxs-lookup"><span data-stu-id="abdb3-601">Change the URL to **/Store/Details/5** to verify the album's information.</span></span>

    <span data-ttu-id="abdb3-602">![瀏覽專輯詳細](aspnet-mvc-4-fundamentals/_static/image32.png "瀏覽專輯詳細資料")</span><span class="sxs-lookup"><span data-stu-id="abdb3-602">![Browsing Albums Detail](aspnet-mvc-4-fundamentals/_static/image32.png "Browsing Albums Detail")</span></span>

    <span data-ttu-id="abdb3-603">*瀏覽專輯的詳細資料*</span><span class="sxs-lookup"><span data-stu-id="abdb3-603">*Browsing Album's Detail*</span></span>

<a id="Ex6Task8"></a>

<a id="Task_8_-_Adding_Links_Between_Pages"></a>
#### <a name="task-8---adding-links-between-pages"></a><span data-ttu-id="abdb3-604">工作 8： 加入頁面之間的連結</span><span class="sxs-lookup"><span data-stu-id="abdb3-604">Task 8 - Adding Links Between Pages</span></span>

<span data-ttu-id="abdb3-605">在這個工作中，您會加入要設為適當的每個內容類型名稱中有一個連結的存放區檢視中的連結**/存放區/瀏覽**URL。</span><span class="sxs-lookup"><span data-stu-id="abdb3-605">In this task, you will add a link in the Store View to have a link in every Genre name to the appropriate **/Store/Browse** URL.</span></span> <span data-ttu-id="abdb3-606">如此一來，當您按一下 內容類型，例如**Disco**，它會瀏覽至**/存放區/瀏覽？ 內容類型 = Disco** URL。</span><span class="sxs-lookup"><span data-stu-id="abdb3-606">This way, when you click on a Genre, for instance **Disco**, it will navigate to **/Store/Browse?genre=Disco** URL.</span></span>

1. <span data-ttu-id="abdb3-607">關閉瀏覽器，如有需要若要返回 Visual Studio 視窗。</span><span class="sxs-lookup"><span data-stu-id="abdb3-607">Close the browser if needed, to return to the Visual Studio window.</span></span> <span data-ttu-id="abdb3-608">更新**索引**頁面以新增連結**瀏覽**頁面。</span><span class="sxs-lookup"><span data-stu-id="abdb3-608">Update the **Index** page to add a link to the **Browse** page.</span></span> <span data-ttu-id="abdb3-609">若要這樣做，請在**方案總管 中**展開**檢視**資料夾，然後在**存放區**資料夾，然後按兩下**Index.cshtml**頁面。</span><span class="sxs-lookup"><span data-stu-id="abdb3-609">To do this, in the **Solution Explorer** expand the **Views** folder, then the **Store** folder and double-click the **Index.cshtml** page.</span></span>
2. <span data-ttu-id="abdb3-610">表示內容類型選取 [瀏覽] 檢視中加入的連結。</span><span class="sxs-lookup"><span data-stu-id="abdb3-610">Add a link to the Browse view indicating the genre selected.</span></span> <span data-ttu-id="abdb3-611">若要這樣做，請取代下列反白顯示的程式碼內 **&lt;li&gt;** 標記: (C#)</span><span class="sxs-lookup"><span data-stu-id="abdb3-611">To do this, replace the following highlighted code within the **&lt;li&gt;** tags: (C#)</span></span>

    [!code-cshtml[Main](aspnet-mvc-4-fundamentals/samples/sample25.cshtml)]

    > [!NOTE]
    > <span data-ttu-id="abdb3-612">另一種方法就直接連結到頁面上，具有類似下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="abdb3-612">another approach would be linking directly to the page, with a code like the following:</span></span>
    > 
    > <span data-ttu-id="abdb3-613">&lt;a =&quot;/存放區/瀏覽？ 內容類型 =@genreName&quot;&gt;@genreName &lt; /a&gt;</span><span class="sxs-lookup"><span data-stu-id="abdb3-613">&lt;a href=&quot;/Store/Browse?genre=@genreName&quot;&gt;@genreName&lt;/a&gt;</span></span>
    > 
    > <span data-ttu-id="abdb3-614">雖然這個方法的效果，它會相依於硬式編碼字串。</span><span class="sxs-lookup"><span data-stu-id="abdb3-614">Although this approach works, it depends on a hardcoded string.</span></span> <span data-ttu-id="abdb3-615">如果您稍後重新命名的控制站，您必須手動變更此指示。</span><span class="sxs-lookup"><span data-stu-id="abdb3-615">If you later rename the Controller, you will have to change this instruction manually.</span></span> <span data-ttu-id="abdb3-616">較佳替代方式是使用**HTML Helper**方法。</span><span class="sxs-lookup"><span data-stu-id="abdb3-616">A better alternative is to use an **HTML Helper** method.</span></span> <span data-ttu-id="abdb3-617">ASP.NET MVC 包括 HTML Helper 方法，這個方法會使用這類工作。</span><span class="sxs-lookup"><span data-stu-id="abdb3-617">ASP.NET MVC includes an HTML Helper method which is available for such tasks.</span></span> <span data-ttu-id="abdb3-618">**Html.ActionLink()** helper 方法可讓您輕鬆地建立 HTML  **&lt;&gt;** 連結，並確定具有正確的 URL 路徑 URL 編碼。</span><span class="sxs-lookup"><span data-stu-id="abdb3-618">The **Html.ActionLink()** helper method makes it easy to build HTML **&lt;a&gt;** links, making sure URL paths are properly URL encoded.</span></span>
    > 
    > <span data-ttu-id="abdb3-619">Htlm.ActionLink 有數個多載。</span><span class="sxs-lookup"><span data-stu-id="abdb3-619">Htlm.ActionLink has several overloads.</span></span> <span data-ttu-id="abdb3-620">在這個練習中您將使用其中一個採用三個參數：</span><span class="sxs-lookup"><span data-stu-id="abdb3-620">In this exercise you will use one that takes three parameters:</span></span>
    > 
    > 1. <span data-ttu-id="abdb3-621">連結文字，將會顯示類型名稱</span><span class="sxs-lookup"><span data-stu-id="abdb3-621">Link text, which will display the Genre name</span></span>
    > 2. <span data-ttu-id="abdb3-622">控制器動作的名稱 (**瀏覽**)</span><span class="sxs-lookup"><span data-stu-id="abdb3-622">Controller action name (**Browse**)</span></span>
    > 3. <span data-ttu-id="abdb3-623">路由參數值，指定兩個名稱 (**類型**) 和值 (**內容類型名稱**)</span><span class="sxs-lookup"><span data-stu-id="abdb3-623">Route parameter values, specifying both the name (**Genre**) and the value (**Genre name**)</span></span>

<a id="Ex6Task9"></a>

<a id="Task_9_-_Running_the_Application"></a>
#### <a name="task-9---running-the-application"></a><span data-ttu-id="abdb3-624">工作 9： 執行應用程式</span><span class="sxs-lookup"><span data-stu-id="abdb3-624">Task 9 - Running the Application</span></span>

<span data-ttu-id="abdb3-625">在這個工作中，您會測試每種內容類型會顯示適當的連結**/存放區/瀏覽**URL。</span><span class="sxs-lookup"><span data-stu-id="abdb3-625">In this task, you will test that each Genre is displayed with a link to the appropriate **/Store/Browse** URL.</span></span>

1. <span data-ttu-id="abdb3-626">按**F5**執行應用程式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-626">Press **F5** to run the Application.</span></span>
2. <span data-ttu-id="abdb3-627">在首頁上，啟動專案。</span><span class="sxs-lookup"><span data-stu-id="abdb3-627">The project starts in the Home page.</span></span> <span data-ttu-id="abdb3-628">將 URL 變更為**/儲存**以確認每個內容類型連結至適當**/存放區/瀏覽**URL。</span><span class="sxs-lookup"><span data-stu-id="abdb3-628">Change the URL to **/Store** to verify that each Genre links to the appropriate **/Store/Browse** URL.</span></span>

    <span data-ttu-id="abdb3-629">![瀏覽連結來瀏覽 頁面的內容類型](aspnet-mvc-4-fundamentals/_static/image33.png "瀏覽連結來瀏覽 頁面的內容類型")</span><span class="sxs-lookup"><span data-stu-id="abdb3-629">![Browsing Genres with links to Browse page](aspnet-mvc-4-fundamentals/_static/image33.png "Browsing Genres with links to Browse page")</span></span>

    <span data-ttu-id="abdb3-630">*瀏覽的內容類型，瀏覽 頁面的連結*</span><span class="sxs-lookup"><span data-stu-id="abdb3-630">*Browsing Genres with links to Browse page*</span></span>

<a id="Ex6Task10"></a>

<a id="Task_10_-_Using_Dynamic_ViewModel_Collection_to_Pass_Values"></a>
#### <a name="task-10---using-dynamic-viewmodel-collection-to-pass-values"></a><span data-ttu-id="abdb3-631">工作 10-使用動態 ViewModel 集合來傳遞值</span><span class="sxs-lookup"><span data-stu-id="abdb3-631">Task 10 - Using Dynamic ViewModel Collection to Pass Values</span></span>

<span data-ttu-id="abdb3-632">在這項工作，您將學習的簡單且功能強大的方法，將控制器和檢視之間傳遞值，而不進行任何變更模型中。</span><span class="sxs-lookup"><span data-stu-id="abdb3-632">In this task, you will learn a simple and powerful method to pass values between the Controller and the View without making any changes in the Model.</span></span> <span data-ttu-id="abdb3-633">ASP.NET MVC 4 提供集合&quot;ViewModel&quot;，它可以指派給任何動態的值和控制器和檢視以及內存取。</span><span class="sxs-lookup"><span data-stu-id="abdb3-633">ASP.NET MVC 4 provides the collection &quot;ViewModel&quot;, which can be assigned to any dynamic value and accessed inside controllers and views as well.</span></span>

<span data-ttu-id="abdb3-634">您現在將使用 ViewBag 動態集合傳遞一份&quot;**起子頭內容類型**&quot;從控制器到檢視。</span><span class="sxs-lookup"><span data-stu-id="abdb3-634">You will now use the ViewBag dynamic collection to pass a list of &quot;**Starred genres**&quot; from the controller to the view.</span></span> <span data-ttu-id="abdb3-635">存放區索引檢視將存取以**ViewModel**並顯示資訊。</span><span class="sxs-lookup"><span data-stu-id="abdb3-635">The Store Index view will access to **ViewModel** and display the information.</span></span>

1. <span data-ttu-id="abdb3-636">關閉瀏覽器，如有需要若要返回 Visual Studio 視窗。</span><span class="sxs-lookup"><span data-stu-id="abdb3-636">Close the browser if needed, to return to the Visual Studio window.</span></span> <span data-ttu-id="abdb3-637">開啟**StoreController.cs**和修改**索引**方法來建立一份起子頭插入 ViewModel 集合的內容類型：</span><span class="sxs-lookup"><span data-stu-id="abdb3-637">Open **StoreController.cs** and modify **Index** method to create a list of starred genres into ViewModel collection :</span></span>


    [!code-csharp[Main](aspnet-mvc-4-fundamentals/samples/sample26.cs)]

    > [!NOTE]
    > <span data-ttu-id="abdb3-638">您也可以使用語法**ViewBag [&quot;Starred&quot;]**來存取屬性。</span><span class="sxs-lookup"><span data-stu-id="abdb3-638">You could also use the syntax **ViewBag[&quot;Starred&quot;]** to access the properties.</span></span>
2. <span data-ttu-id="abdb3-639">星狀圖示 **&quot;starred.png&quot;** 隨附於**Source\Assets\Images**本實驗室的資料夾。</span><span class="sxs-lookup"><span data-stu-id="abdb3-639">The star icon **&quot;starred.png&quot;** is included in the **Source\Assets\Images** folder of this lab.</span></span> <span data-ttu-id="abdb3-640">將它加入至應用程式中，拖曳其內容從**Windows 檔案總管**到視窗**方案總管 中**在 Visual Web Developer Express 中，如下所示：</span><span class="sxs-lookup"><span data-stu-id="abdb3-640">In order to add it to the application, drag their content from a **Windows Explorer** window into the **Solution Explorer** in Visual Web Developer Express, as shown below:</span></span>

    <span data-ttu-id="abdb3-641">![加入至方案的星型映像](aspnet-mvc-4-fundamentals/_static/image34.png "加入至方案的星型映像")</span><span class="sxs-lookup"><span data-stu-id="abdb3-641">![Adding star image to the solution](aspnet-mvc-4-fundamentals/_static/image34.png "Adding star image to the solution")</span></span>

    <span data-ttu-id="abdb3-642">*星型的映像新增到方案*</span><span class="sxs-lookup"><span data-stu-id="abdb3-642">*Adding star image to the solution*</span></span>
3. <span data-ttu-id="abdb3-643">開啟檢視**Store/Index.cshtml**和修改內容。</span><span class="sxs-lookup"><span data-stu-id="abdb3-643">Open the view **Store/Index.cshtml** and modify the content.</span></span> <span data-ttu-id="abdb3-644">將讀取&quot;起子頭&quot;屬性**ViewBag**集合，並詢問是否目前的內容類型名稱清單中。</span><span class="sxs-lookup"><span data-stu-id="abdb3-644">You will read the &quot;starred&quot; property in the **ViewBag** collection, and ask if the current genre name is in the list.</span></span> <span data-ttu-id="abdb3-645">在此情況下，您會顯示由右至內容類型連結以星號圖示。</span><span class="sxs-lookup"><span data-stu-id="abdb3-645">In that case you will show a star icon right to the genre link.</span></span>
<span data-ttu-id="abdb3-646">(C#)</span><span class="sxs-lookup"><span data-stu-id="abdb3-646">(C#)</span></span>

    [!code-cshtml[Main](aspnet-mvc-4-fundamentals/samples/sample27.cshtml)]

<a id="Ex6Task11"></a>

<a id="Task_11_-_Running_the_Application"></a>
#### <a name="task-11---running-the-application"></a><span data-ttu-id="abdb3-647">工作 11-執行應用程式</span><span class="sxs-lookup"><span data-stu-id="abdb3-647">Task 11 - Running the Application</span></span>

<span data-ttu-id="abdb3-648">在這項工作，您將測試，如星號所指的內容類型會顯示以星號圖示。</span><span class="sxs-lookup"><span data-stu-id="abdb3-648">In this task, you will test that the starred genres display a star icon.</span></span>

1. <span data-ttu-id="abdb3-649">按**F5**執行應用程式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-649">Press **F5** to run the Application.</span></span>
2. <span data-ttu-id="abdb3-650">在專案開始**首頁**頁面。</span><span class="sxs-lookup"><span data-stu-id="abdb3-650">The project starts in the **Home** page.</span></span> <span data-ttu-id="abdb3-651">將 URL 變更為**/儲存**以確定每個精選內容類型有 respecting 標籤：</span><span class="sxs-lookup"><span data-stu-id="abdb3-651">Change the URL to **/Store** to verify that each featured genre has the respecting label:</span></span>

    <span data-ttu-id="abdb3-652">![瀏覽內容類型，使用如星號所指的項目](aspnet-mvc-4-fundamentals/_static/image35.png "瀏覽內容類型，使用如星號所指的項目")</span><span class="sxs-lookup"><span data-stu-id="abdb3-652">![Browsing Genres with starred elements](aspnet-mvc-4-fundamentals/_static/image35.png "Browsing Genres with starred elements")</span></span>

    <span data-ttu-id="abdb3-653">*瀏覽的內容類型，使用如星號所指的項目*</span><span class="sxs-lookup"><span data-stu-id="abdb3-653">*Browsing Genres with starred elements*</span></span>

<a id="Exercise7"></a>

<a id="Exercise_7_A_lap_around_ASPNET_MVC_4_new_template"></a>
### <a name="exercise-7-a-lap-around-aspnet-mvc-4-new-template"></a><span data-ttu-id="abdb3-654">練習 7： 一圈住 ASP.NET MVC 4 的新範本</span><span class="sxs-lookup"><span data-stu-id="abdb3-654">Exercise 7: A lap around ASP.NET MVC 4 new template</span></span>

<span data-ttu-id="abdb3-655">在此練習中，您將探索的增強功能，在 ASP.NET MVC 4 專案範本中，採取一起來看看新範本的最相關的功能。</span><span class="sxs-lookup"><span data-stu-id="abdb3-655">In this exercise, you will explore the enhancements in the ASP.NET MVC 4 project templates, taking a look at the most relevant features of the new template.</span></span>

<a id="Ex7Task1"></a>

<a id="Task_1_Exploring_the_ASPNET_MVC_4_Internet_Application_Template"></a>
#### <a name="task-1-exploring-the-aspnet-mvc-4-internet-application-template"></a><span data-ttu-id="abdb3-656">工作 1： 瀏覽 ASP.NET MVC 4 網際網路應用程式範本</span><span class="sxs-lookup"><span data-stu-id="abdb3-656">Task 1: Exploring the ASP.NET MVC 4 Internet Application Template</span></span>

1. <span data-ttu-id="abdb3-657">如果尚未開啟，啟動**VS Express for Web**</span><span class="sxs-lookup"><span data-stu-id="abdb3-657">If not already open, start **VS Express for Web**</span></span>
2. <span data-ttu-id="abdb3-658">選取**檔案 |新 |專案**功能表命令。</span><span class="sxs-lookup"><span data-stu-id="abdb3-658">Select the **File | New | Project** menu command.</span></span> <span data-ttu-id="abdb3-659">在**新專案**對話方塊中，選取**Visual C# |Web**在左窗格中的範本樹狀結構，然後選擇  **ASP.NET MVC 4 Web 應用程式**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-659">In the **New Project** dialog, select the **Visual C#|Web** template on the left pane tree, and choose the **ASP.NET MVC 4 Web Application**.</span></span> <span data-ttu-id="abdb3-660">**名稱**專案*MusicStore*並更新**方案名稱**至*開始*，然後選取一個位置 （或保留預設值），按一下  **確定**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-660">**Name** the project *MusicStore* and update the **solution name** to *Begin*, then select a location (or leave the default) and click **OK**.</span></span>

    <span data-ttu-id="abdb3-661">![建立新的 ASP.NET MVC 4 專案](aspnet-mvc-4-fundamentals/_static/image36.png "建立新的 ASP.NET MVC 4 專案")</span><span class="sxs-lookup"><span data-stu-id="abdb3-661">![Creating a new ASP.NET MVC 4 Project](aspnet-mvc-4-fundamentals/_static/image36.png "Creating a new ASP.NET MVC 4 Project")</span></span>

    <span data-ttu-id="abdb3-662">*建立新的 ASP.NET MVC 4 專案*</span><span class="sxs-lookup"><span data-stu-id="abdb3-662">*Creating a new ASP.NET MVC 4 Project*</span></span>
3. <span data-ttu-id="abdb3-663">在**新增 ASP.NET MVC 4 專案**對話方塊中，選取**網際網路應用程式**專案範本，然後按一下**確定**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-663">In the **New ASP.NET MVC 4 Project** dialog, select the **Internet Application** project template and click **OK**.</span></span> <span data-ttu-id="abdb3-664">請注意，您可以選取 Razor 或 ASPX 做為檢視引擎。</span><span class="sxs-lookup"><span data-stu-id="abdb3-664">Notice you can select either Razor or ASPX as the view engine.</span></span>

    <span data-ttu-id="abdb3-665">![建立新 ASP.NET MVC 4 網際網路應用程式](aspnet-mvc-4-fundamentals/_static/image37.png "建立新 ASP.NET MVC 4 網際網路應用程式")</span><span class="sxs-lookup"><span data-stu-id="abdb3-665">![Creating a new ASP.NET MVC 4 Internet Application](aspnet-mvc-4-fundamentals/_static/image37.png "Creating a new ASP.NET MVC 4 Internet Application")</span></span>

    <span data-ttu-id="abdb3-666">*建立新 ASP.NET MVC 4 網際網路應用程式*</span><span class="sxs-lookup"><span data-stu-id="abdb3-666">*Creating a new ASP.NET MVC 4 Internet Application*</span></span>

    > [!NOTE]
    > <span data-ttu-id="abdb3-667">ASP.NET MVC 3 中已經導入 razor 語法。</span><span class="sxs-lookup"><span data-stu-id="abdb3-667">Razor syntax has been introduced in ASP.NET MVC 3.</span></span> <span data-ttu-id="abdb3-668">其目的是字元和所需在檔案中，啟用快速和程式碼撰寫工作流程的流體按鍵數目降至最低。</span><span class="sxs-lookup"><span data-stu-id="abdb3-668">Its goal is to minimize the number of characters and keystrokes required in a file, enabling a fast and fluid coding workflow.</span></span> <span data-ttu-id="abdb3-669">Razor 運用現有 C# /VB （或其他） 的語言能力，並傳遞可讓實用的 HTML 建構工作流程範本標記語法。</span><span class="sxs-lookup"><span data-stu-id="abdb3-669">Razor leverages existing C#/VB (or other) language skills and delivers a template markup syntax that enables an awesome HTML construction workflow.</span></span>
4. <span data-ttu-id="abdb3-670">按**F5**執行方案，並查看更新的範本。</span><span class="sxs-lookup"><span data-stu-id="abdb3-670">Press **F5** to run the solution and see the renewed template.</span></span> <span data-ttu-id="abdb3-671">您可以查看下列功能：</span><span class="sxs-lookup"><span data-stu-id="abdb3-671">You can check out the following features:</span></span>

    1. <span data-ttu-id="abdb3-672">**現代化樣式範本**</span><span class="sxs-lookup"><span data-stu-id="abdb3-672">**Modern-style templates**</span></span>

        <span data-ttu-id="abdb3-673">已經更新的範本，提供更多現代尋找樣式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-673">The templates have been renewed, providing more modern-looking styles.</span></span>

        <span data-ttu-id="abdb3-674">![ASP.NET MVC 4 重新設定樣式範本](aspnet-mvc-4-fundamentals/_static/image38.png "ASP.NET MVC 4 重新設定樣式，範本")</span><span class="sxs-lookup"><span data-stu-id="abdb3-674">![ASP.NET MVC 4 restyled templates](aspnet-mvc-4-fundamentals/_static/image38.png "ASP.NET MVC 4 restyled templates")</span></span>

        <span data-ttu-id="abdb3-675">*ASP.NET MVC 4 重新設定樣式範本*</span><span class="sxs-lookup"><span data-stu-id="abdb3-675">*ASP.NET MVC 4 restyled templates*</span></span>
    2. <span data-ttu-id="abdb3-676">**調整呈現**</span><span class="sxs-lookup"><span data-stu-id="abdb3-676">**Adaptive Rendering**</span></span>

        <span data-ttu-id="abdb3-677">簽出調整瀏覽器視窗，並注意如何頁面配置動態適應新的視窗大小。</span><span class="sxs-lookup"><span data-stu-id="abdb3-677">Check out resizing the browser window and notice how the page layout dynamically adapts to the new window size.</span></span> <span data-ttu-id="abdb3-678">這些範本會使用適應性呈現技術，在桌上型電腦和行動平台，而無需自訂正確轉譯。</span><span class="sxs-lookup"><span data-stu-id="abdb3-678">These templates use the adaptive rendering technique to render properly in both desktop and mobile platforms without any customization.</span></span>

        <span data-ttu-id="abdb3-679">![ASP.NET MVC 4 專案範本中不同的瀏覽器大小](aspnet-mvc-4-fundamentals/_static/image39.png "ASP.NET MVC 4 專案範本中不同的瀏覽器的大小")</span><span class="sxs-lookup"><span data-stu-id="abdb3-679">![ASP.NET MVC 4 project template in different browser sizes](aspnet-mvc-4-fundamentals/_static/image39.png "ASP.NET MVC 4 project template in different browser sizes")</span></span>

        <span data-ttu-id="abdb3-680">*ASP.NET MVC 4 專案範本中不同的瀏覽器的大小*</span><span class="sxs-lookup"><span data-stu-id="abdb3-680">*ASP.NET MVC 4 project template in different browser sizes*</span></span>
5. <span data-ttu-id="abdb3-681">關閉瀏覽器以停止偵錯工具，並返回 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="abdb3-681">Close the browser to stop the debugger and return to Visual Studio.</span></span>
6. <span data-ttu-id="abdb3-682">現在，您就能夠瀏覽方案，並查看一些由 ASP.NET MVC 4 專案範本所引進的新功能。</span><span class="sxs-lookup"><span data-stu-id="abdb3-682">Now you are able to explore the solution and check out some of the new features introduced by ASP.NET MVC 4 in the project template.</span></span>

    <span data-ttu-id="abdb3-683">![ASP.NET MVC4 網際網路-應用程式的專案-樣板](aspnet-mvc-4-fundamentals/_static/image40.png "ASP.NET MVC 4 網際網路應用程式專案範本")</span><span class="sxs-lookup"><span data-stu-id="abdb3-683">![ASP.NET MVC4-internet-application-project-template](aspnet-mvc-4-fundamentals/_static/image40.png "The ASP.NET MVC 4 Internet Application Project Template")</span></span>

    <span data-ttu-id="abdb3-684">*ASP.NET MVC 4 網際網路應用程式專案範本*</span><span class="sxs-lookup"><span data-stu-id="abdb3-684">*The ASP.NET MVC 4 Internet Application Project Template*</span></span>

    1. <span data-ttu-id="abdb3-685">**HTML5 標記**</span><span class="sxs-lookup"><span data-stu-id="abdb3-685">**HTML5 markup**</span></span>

        <span data-ttu-id="abdb3-686">瀏覽以找出新的佈景主題標記，例如開啟範本檢視**About.cshtml**內檢視**首頁**資料夾。</span><span class="sxs-lookup"><span data-stu-id="abdb3-686">Browse template views to find out the new theme markup, for example open **About.cshtml** view within **Home** folder.</span></span>

        <span data-ttu-id="abdb3-687">![新的範本，使用 Razor 和 HTML5 標記](aspnet-mvc-4-fundamentals/_static/image41.png "新範本，使用 Razor 和 HTML5 的標記")</span><span class="sxs-lookup"><span data-stu-id="abdb3-687">![New template, using Razor and HTML5 markup](aspnet-mvc-4-fundamentals/_static/image41.png "New template, using Razor and HTML5 markup")</span></span>

        <span data-ttu-id="abdb3-688">*新的範本，使用 Razor 和 HTML5 的標記*</span><span class="sxs-lookup"><span data-stu-id="abdb3-688">*New template, using Razor and HTML5 markup*</span></span>
    2. <span data-ttu-id="abdb3-689">**包含的 JavaScript 程式庫**</span><span class="sxs-lookup"><span data-stu-id="abdb3-689">**JavaScript libraries included**</span></span>

        1. <span data-ttu-id="abdb3-690">**jQuery**: jQuery 簡化 HTML 文件周遊、 事件處理、 建立動畫，以及 Ajax 互動。</span><span class="sxs-lookup"><span data-stu-id="abdb3-690">**jQuery**: jQuery simplifies HTML document traversing, event handling, animating, and Ajax interactions.</span></span>
        2. <span data-ttu-id="abdb3-691">**jQuery UI**： 此程式庫提供針對低層級互動和進階效果的動畫主題化 widget，之上 jQuery JavaScript 程式庫的抽象概念。</span><span class="sxs-lookup"><span data-stu-id="abdb3-691">**jQuery UI**: This library provides abstractions for low-level interaction and animation, advanced effects and themeable widgets, built on top of the jQuery JavaScript Library.</span></span>

            > [!NOTE]
            > <span data-ttu-id="abdb3-692">您可以了解 jQuery 和 jQuery UI 中[ [http://docs.jquery.com/](http://docs.jquery.com/)](http://docs.jquery.com/)。</span><span class="sxs-lookup"><span data-stu-id="abdb3-692">You can learn about jQuery and jQuery UI in [[http://docs.jquery.com/](http://docs.jquery.com/)](http://docs.jquery.com/).</span></span>
        3. <span data-ttu-id="abdb3-693">**KnockoutJS**: ASP.NET MVC 4 預設範本現在包含**KnockoutJS**，可讓您建立豐富且高回應性的 web 應用程式使用 JavaScript 和 HTML 的 JavaScript MVVM 架構。</span><span class="sxs-lookup"><span data-stu-id="abdb3-693">**KnockoutJS**: The ASP.NET MVC 4 default template now includes **KnockoutJS**, a JavaScript MVVM framework that lets you create rich and highly responsive web applications using JavaScript and HTML.</span></span> <span data-ttu-id="abdb3-694">例如在 ASP.NET MVC 3 中，jQuery 和 jQuery UI 程式庫也包含在 ASP.NET MVC 4。</span><span class="sxs-lookup"><span data-stu-id="abdb3-694">Like in ASP.NET MVC 3, jQuery and jQuery UI libraries are also included in ASP.NET MVC 4.</span></span>

            > [!NOTE]
            > <span data-ttu-id="abdb3-695">您可以取得有關 KnockOutJS 此連結中的程式庫的詳細資訊： [http://learn.knockoutjs.com/](http://learn.knockoutjs.com/)。</span><span class="sxs-lookup"><span data-stu-id="abdb3-695">You can get more information about KnockOutJS library in this link: [http://learn.knockoutjs.com/](http://learn.knockoutjs.com/).</span></span>
        4. <span data-ttu-id="abdb3-696">**Modernizr**： 此文件庫會自動執行，讓您的網站與舊的瀏覽器相容，使用 HTML5 和 CSS3 的技術時。</span><span class="sxs-lookup"><span data-stu-id="abdb3-696">**Modernizr**: This library runs automatically, making your site compatible with older browsers when using HTML5 and CSS3 technologies.</span></span>

            > [!NOTE]
            > <span data-ttu-id="abdb3-697">您可以取得此連結中的 Modernizr 程式庫的詳細資訊： [http://www.modernizr.com/](http://www.modernizr.com/)。</span><span class="sxs-lookup"><span data-stu-id="abdb3-697">You can get more information about Modernizr library in this link: [http://www.modernizr.com/](http://www.modernizr.com/).</span></span>
    3. <span data-ttu-id="abdb3-698">**包含在方案中的 SimpleMembership**</span><span class="sxs-lookup"><span data-stu-id="abdb3-698">**SimpleMembership included in the solution**</span></span>

        <span data-ttu-id="abdb3-699">SimpleMembership 已經設計為先前的 ASP.NET 角色和成員資格提供者系統的取代項目。</span><span class="sxs-lookup"><span data-stu-id="abdb3-699">SimpleMembership has been designed as a replacement for the previous ASP.NET Role and Membership provider system.</span></span> <span data-ttu-id="abdb3-700">它有許多新功能，讓您輕鬆安全的網頁開發人員更有彈性的方式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-700">It has many new features that make it easier for the developer to secure web pages in a more flexible way.</span></span>

        <span data-ttu-id="abdb3-701">網際網路範本已經有設定整合 SimpleMembership 幾件事，例如 AccountController 已準備好要使用 OAuthWebSecurity （適用於 OAuth 帳戶註冊、 登入、 管理等） 和 Web 的安全性。</span><span class="sxs-lookup"><span data-stu-id="abdb3-701">The Internet template already has set up a few things to integrate SimpleMembership, for example, the AccountController is prepared to use OAuthWebSecurity (for OAuth account registration, login, management, etc.) and Web Security.</span></span>

        <span data-ttu-id="abdb3-702">![包含在解決方案中 SimpleMembership](aspnet-mvc-4-fundamentals/_static/image42.png "SimpleMembership 包含在方案中")</span><span class="sxs-lookup"><span data-stu-id="abdb3-702">![SimpleMembership Included in the solution](aspnet-mvc-4-fundamentals/_static/image42.png "SimpleMembership Included in the solution")</span></span>

        <span data-ttu-id="abdb3-703">*包含在解決方案中 SimpleMembership*</span><span class="sxs-lookup"><span data-stu-id="abdb3-703">*SimpleMembership Included in the solution*</span></span>

        > [!NOTE]
        > <span data-ttu-id="abdb3-704">更多關於[OAuthWebSecurity](https://msdn.microsoft.com/en-us/library/jj158393(v=vs.111).aspx) MSDN 中。</span><span class="sxs-lookup"><span data-stu-id="abdb3-704">Find more information about [OAuthWebSecurity](https://msdn.microsoft.com/en-us/library/jj158393(v=vs.111).aspx) in MSDN.</span></span>

> [!NOTE]
> <span data-ttu-id="abdb3-705">此外，您可以部署此應用程式以 Windows Azure Web Sites 下列[附錄 b： 發佈 ASP.NET MVC 4 應用程式使用 Web Deploy](#AppendixB)。</span><span class="sxs-lookup"><span data-stu-id="abdb3-705">Additionally, you can deploy this application to Windows Azure Web Sites following [Appendix B: Publishing an ASP.NET MVC 4 Application using Web Deploy](#AppendixB).</span></span>


* * *

<a id="Summary"></a>

<a id="Summary"></a>
## <a name="summary"></a><span data-ttu-id="abdb3-706">總結</span><span class="sxs-lookup"><span data-stu-id="abdb3-706">Summary</span></span>

<span data-ttu-id="abdb3-707">藉由完成這個實際操作實驗室中，您已經學會 ASP.NET MVC 的基本概念：</span><span class="sxs-lookup"><span data-stu-id="abdb3-707">By completing this Hands-On Lab you have learned the fundamentals of ASP.NET MVC:</span></span>

- <span data-ttu-id="abdb3-708">MVC 應用程式，以及它們如何互動的核心項目</span><span class="sxs-lookup"><span data-stu-id="abdb3-708">The core elements of an MVC application and how they interact</span></span>
- <span data-ttu-id="abdb3-709">如何建立 ASP.NET MVC 應用程式</span><span class="sxs-lookup"><span data-stu-id="abdb3-709">How to create an ASP.NET MVC Application</span></span>
- <span data-ttu-id="abdb3-710">如何新增及設定控制站來處理參數傳遞的 URL 和查詢字串</span><span class="sxs-lookup"><span data-stu-id="abdb3-710">How to add and configure Controllers to handle parameters passed through the URL and querystring</span></span>
- <span data-ttu-id="abdb3-711">如何新增配置主版頁面設定一般的 HTML 內容，以提升外觀及操作，並檢視範本以顯示 HTML 內容的樣式表的範本</span><span class="sxs-lookup"><span data-stu-id="abdb3-711">How to add a layout master page to setup a template for common HTML content, a StyleSheet to enhance the look and feel and a View template to display HTML content</span></span>
- <span data-ttu-id="abdb3-712">如何將內容傳遞至檢視表範本使用 ViewModel 模式，來顯示動態資訊</span><span class="sxs-lookup"><span data-stu-id="abdb3-712">How to use the ViewModel pattern for passing properties to the View template to display dynamic information</span></span>
- <span data-ttu-id="abdb3-713">如何使用傳遞至控制器，檢視範本中的參數</span><span class="sxs-lookup"><span data-stu-id="abdb3-713">How to use parameters passed to Controllers in the View template</span></span>
- <span data-ttu-id="abdb3-714">如何將連結加入至 ASP.NET MVC 應用程式內的頁面</span><span class="sxs-lookup"><span data-stu-id="abdb3-714">How to add links to pages inside the ASP.NET MVC application</span></span>
- <span data-ttu-id="abdb3-715">如何加入和檢視中使用動態屬性</span><span class="sxs-lookup"><span data-stu-id="abdb3-715">How to add and use dynamic properties in a View</span></span>
- <span data-ttu-id="abdb3-716">ASP.NET MVC 4 專案範本中的增強功能</span><span class="sxs-lookup"><span data-stu-id="abdb3-716">The enhancements in the ASP.NET MVC 4 project templates</span></span>

<a id="AppendixA"></a>

<a id="Appendix_A_Installing_Visual_Studio_Express_2012_for_Web"></a>
## <a name="appendix-a-installing-visual-studio-express-2012-for-web"></a><span data-ttu-id="abdb3-717">附錄 a： 安裝 Visual Studio Express 2012 for Web</span><span class="sxs-lookup"><span data-stu-id="abdb3-717">Appendix A: Installing Visual Studio Express 2012 for Web</span></span>

<span data-ttu-id="abdb3-718">您可以安裝**Microsoft Visual Studio Express 2012 for Web**或另一個&quot;Express&quot;版本使用 **[Microsoft Web Platform Installer](https://www.microsoft.com/web/downloads/platform.aspx)** .</span><span class="sxs-lookup"><span data-stu-id="abdb3-718">You can install **Microsoft Visual Studio Express 2012 for Web** or another &quot;Express&quot; version using the **[Microsoft Web Platform Installer](https://www.microsoft.com/web/downloads/platform.aspx)**.</span></span> <span data-ttu-id="abdb3-719">下列指示將引導您逐步完成安裝所需*Visual studio Express 2012 for Web*使用*Microsoft Web Platform Installer*。</span><span class="sxs-lookup"><span data-stu-id="abdb3-719">The following instructions guide you through the steps required to install *Visual studio Express 2012 for Web* using *Microsoft Web Platform Installer*.</span></span>

1. <span data-ttu-id="abdb3-720">移至[ [https://go.microsoft.com/?linkid=9810169](https://go.microsoft.com/?linkid=9810169)](https://go.microsoft.com/?linkid=9810169)。</span><span class="sxs-lookup"><span data-stu-id="abdb3-720">Go to [[https://go.microsoft.com/?linkid=9810169](https://go.microsoft.com/?linkid=9810169)](https://go.microsoft.com/?linkid=9810169).</span></span> <span data-ttu-id="abdb3-721">或者，如果您已安裝 Web Platform Installer，您可以開啟它，並搜尋產品&quot; *Visual Studio Express 2012 for Web 與 Windows Azure SDK*&quot;。</span><span class="sxs-lookup"><span data-stu-id="abdb3-721">Alternatively, if you already have installed Web Platform Installer, you can open it and search for the product &quot;*Visual Studio Express 2012 for Web with Windows Azure SDK*&quot;.</span></span>
2. <span data-ttu-id="abdb3-722">按一下**立即安裝**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-722">Click on **Install Now**.</span></span> <span data-ttu-id="abdb3-723">如果您不需要**Web Platform Installer**您會重新導向至下載並安裝第一次。</span><span class="sxs-lookup"><span data-stu-id="abdb3-723">If you do not have **Web Platform Installer** you will be redirected to download and install it first.</span></span>
3. <span data-ttu-id="abdb3-724">一次**Web Platform Installer**開啟時，按一下 **安裝**，啟動安裝程式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-724">Once **Web Platform Installer** is open, click **Install** to start the setup.</span></span>

    <span data-ttu-id="abdb3-725">![安裝 Visual Studio Express](aspnet-mvc-4-fundamentals/_static/image43.png "安裝 Visual Studio Express")</span><span class="sxs-lookup"><span data-stu-id="abdb3-725">![Install Visual Studio Express](aspnet-mvc-4-fundamentals/_static/image43.png "Install Visual Studio Express")</span></span>

    <span data-ttu-id="abdb3-726">*安裝 Visual Studio Express*</span><span class="sxs-lookup"><span data-stu-id="abdb3-726">*Install Visual Studio Express*</span></span>
4. <span data-ttu-id="abdb3-727">閱讀所有產品的授權和詞彙，然後按一下**我接受**才能繼續。</span><span class="sxs-lookup"><span data-stu-id="abdb3-727">Read all the products' licenses and terms and click **I Accept** to continue.</span></span>

    ![接受授權條款](aspnet-mvc-4-fundamentals/_static/image44.png)

    <span data-ttu-id="abdb3-729">*接受授權條款*</span><span class="sxs-lookup"><span data-stu-id="abdb3-729">*Accepting the license terms*</span></span>
5. <span data-ttu-id="abdb3-730">等待直到完成下載和安裝程序。</span><span class="sxs-lookup"><span data-stu-id="abdb3-730">Wait until the downloading and installation process completes.</span></span>

    ![安裝進度](aspnet-mvc-4-fundamentals/_static/image45.png)

    <span data-ttu-id="abdb3-732">*安裝進度*</span><span class="sxs-lookup"><span data-stu-id="abdb3-732">*Installation progress*</span></span>
6. <span data-ttu-id="abdb3-733">當安裝完成時，按一下**完成**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-733">When the installation completes, click **Finish**.</span></span>

    ![安裝已完成](aspnet-mvc-4-fundamentals/_static/image46.png)

    <span data-ttu-id="abdb3-735">*安裝已完成*</span><span class="sxs-lookup"><span data-stu-id="abdb3-735">*Installation completed*</span></span>
7. <span data-ttu-id="abdb3-736">按一下**結束**關閉 Web Platform Installer。</span><span class="sxs-lookup"><span data-stu-id="abdb3-736">Click **Exit** to close Web Platform Installer.</span></span>
8. <span data-ttu-id="abdb3-737">若要開啟 Visual Studio Express for Web，請移至**啟動**畫面上，並開始書寫&quot; **VS Express**&quot;，然後按一下  **VS Express for Web**並排顯示。</span><span class="sxs-lookup"><span data-stu-id="abdb3-737">To open Visual Studio Express for Web, go to the **Start** screen and start writing &quot;**VS Express**&quot;, then click on the **VS Express for Web** tile.</span></span>

    ![VS Express for Web 方塊](aspnet-mvc-4-fundamentals/_static/image47.png)

    <span data-ttu-id="abdb3-739">*VS Express for Web 方塊*</span><span class="sxs-lookup"><span data-stu-id="abdb3-739">*VS Express for Web tile*</span></span>

<a id="AppendixB"></a>

<a id="Appendix_B_Publishing_an_ASPNET_MVC_4_Application_using_Web_Deploy"></a>
## <a name="appendix-b-publishing-an-aspnet-mvc-4-application-using-web-deploy"></a><span data-ttu-id="abdb3-740">附錄 b： 發佈 ASP.NET MVC 4 應用程式使用 Web Deploy</span><span class="sxs-lookup"><span data-stu-id="abdb3-740">Appendix B: Publishing an ASP.NET MVC 4 Application using Web Deploy</span></span>

<span data-ttu-id="abdb3-741">此附錄將說明如何從 Windows Azure 管理入口網站建立新的網站和發行您取得依照實驗室中，利用 Web Deploy 發行功能的 Windows Azure 所提供的應用程式。</span><span class="sxs-lookup"><span data-stu-id="abdb3-741">This appendix will show you how to create a new web site from the Windows Azure Management Portal and publish the application you obtained by following the lab, taking advantage of the Web Deploy publishing feature provided by Windows Azure.</span></span>

<a id="ApxBTask1"></a>

<a id="Task_1_-_Creating_a_New_Web_Site_from_the_Windows_Azure_Portal"></a>
#### <a name="task-1---creating-a-new-web-site-from-the-windows-azure-portal"></a><span data-ttu-id="abdb3-742">工作 1-建立新的網站，從 Windows Azure 入口網站</span><span class="sxs-lookup"><span data-stu-id="abdb3-742">Task 1 - Creating a New Web Site from the Windows Azure Portal</span></span>

1. <span data-ttu-id="abdb3-743">移至[Windows Azure 管理入口網站](https://manage.windowsazure.com/)並使用與您訂用帳戶相關聯的 Microsoft 認證登入。</span><span class="sxs-lookup"><span data-stu-id="abdb3-743">Go to the [Windows Azure Management Portal](https://manage.windowsazure.com/) and sign in using the Microsoft credentials associated with your subscription.</span></span>

    > [!NOTE]
    > <span data-ttu-id="abdb3-744">與 Windows Azure 中，您可以免費裝載 10 個 ASP.NET 網站並再擴充隨流量成長。</span><span class="sxs-lookup"><span data-stu-id="abdb3-744">With Windows Azure you can host 10 ASP.NET Web Sites for free and then scale as your traffic grows.</span></span> <span data-ttu-id="abdb3-745">您可以註冊[這裡](http://aka.ms/aspnet-hol-azure)。</span><span class="sxs-lookup"><span data-stu-id="abdb3-745">You can sign up [here](http://aka.ms/aspnet-hol-azure).</span></span>

    <span data-ttu-id="abdb3-746">![登入 Windows Azure 入口網站](aspnet-mvc-4-fundamentals/_static/image48.png "登入 Windows Azure 入口網站")</span><span class="sxs-lookup"><span data-stu-id="abdb3-746">![Log on to Windows Azure portal](aspnet-mvc-4-fundamentals/_static/image48.png "Log on to Windows Azure portal")</span></span>

    <span data-ttu-id="abdb3-747">*登入 Windows Azure 管理入口網站*</span><span class="sxs-lookup"><span data-stu-id="abdb3-747">*Log on to Windows Azure Management Portal*</span></span>
2. <span data-ttu-id="abdb3-748">按一下**新增**命令列上。</span><span class="sxs-lookup"><span data-stu-id="abdb3-748">Click **New** on the command bar.</span></span>

    <span data-ttu-id="abdb3-749">![建立新的網站](aspnet-mvc-4-fundamentals/_static/image49.png "建立新的網站")</span><span class="sxs-lookup"><span data-stu-id="abdb3-749">![Creating a new Web Site](aspnet-mvc-4-fundamentals/_static/image49.png "Creating a new Web Site")</span></span>

    <span data-ttu-id="abdb3-750">*建立新的網站*</span><span class="sxs-lookup"><span data-stu-id="abdb3-750">*Creating a new Web Site*</span></span>
3. <span data-ttu-id="abdb3-751">按一下**計算** | **網站**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-751">Click **Compute** | **Web Site**.</span></span> <span data-ttu-id="abdb3-752">然後選取**快速建立**選項。</span><span class="sxs-lookup"><span data-stu-id="abdb3-752">Then select **Quick Create** option.</span></span> <span data-ttu-id="abdb3-753">新的網站上提供可用的 URL，然後按一下**建立網站**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-753">Provide an available URL for the new web site and click **Create Web Site**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="abdb3-754">Windows Azure 網站是您可以控制和管理在雲端中執行的 web 應用程式的主機。</span><span class="sxs-lookup"><span data-stu-id="abdb3-754">A Windows Azure Web Site is the host for a web application running in the cloud that you can control and manage.</span></span> <span data-ttu-id="abdb3-755">快速建立 選項可讓您部署已完成的 web 應用程式至 Windows Azure 網站從入口網站外部。</span><span class="sxs-lookup"><span data-stu-id="abdb3-755">The Quick Create option allows you to deploy a completed web application to the Windows Azure Web Site from outside the portal.</span></span> <span data-ttu-id="abdb3-756">它不包含設定資料庫的步驟。</span><span class="sxs-lookup"><span data-stu-id="abdb3-756">It does not include steps for setting up a database.</span></span>

    <span data-ttu-id="abdb3-757">![建立新的網站使用 快速建立](aspnet-mvc-4-fundamentals/_static/image50.png "建立新的網站使用 快速建立")</span><span class="sxs-lookup"><span data-stu-id="abdb3-757">![Creating a new Web Site using Quick Create](aspnet-mvc-4-fundamentals/_static/image50.png "Creating a new Web Site using Quick Create")</span></span>

    <span data-ttu-id="abdb3-758">*建立新的網站使用 快速建立*</span><span class="sxs-lookup"><span data-stu-id="abdb3-758">*Creating a new Web Site using Quick Create*</span></span>
4. <span data-ttu-id="abdb3-759">等候新**網站**建立。</span><span class="sxs-lookup"><span data-stu-id="abdb3-759">Wait until the new **Web Site** is created.</span></span>
5. <span data-ttu-id="abdb3-760">建立網站之後按一下底下的連結**URL**資料行。</span><span class="sxs-lookup"><span data-stu-id="abdb3-760">Once the Web Site is created click the link under the **URL** column.</span></span> <span data-ttu-id="abdb3-761">請檢查新的網站運作。</span><span class="sxs-lookup"><span data-stu-id="abdb3-761">Check that the new Web Site is working.</span></span>

    <span data-ttu-id="abdb3-762">![瀏覽至新的網站](aspnet-mvc-4-fundamentals/_static/image51.png "瀏覽至新的網站")</span><span class="sxs-lookup"><span data-stu-id="abdb3-762">![Browsing to the new web site](aspnet-mvc-4-fundamentals/_static/image51.png "Browsing to the new web site")</span></span>

    <span data-ttu-id="abdb3-763">*瀏覽至新的網站*</span><span class="sxs-lookup"><span data-stu-id="abdb3-763">*Browsing to the new web site*</span></span>

    <span data-ttu-id="abdb3-764">![執行網站](aspnet-mvc-4-fundamentals/_static/image52.png "執行的網站")</span><span class="sxs-lookup"><span data-stu-id="abdb3-764">![Web site running](aspnet-mvc-4-fundamentals/_static/image52.png "Web site running")</span></span>

    <span data-ttu-id="abdb3-765">*執行的網站*</span><span class="sxs-lookup"><span data-stu-id="abdb3-765">*Web site running*</span></span>
6. <span data-ttu-id="abdb3-766">返回入口網站並按一下底下的網站名稱**名稱**資料行會顯示 [管理] 頁面。</span><span class="sxs-lookup"><span data-stu-id="abdb3-766">Go back to the portal and click the name of the web site under the **Name** column to display the management pages.</span></span>

    <span data-ttu-id="abdb3-767">![開啟網站管理頁面](aspnet-mvc-4-fundamentals/_static/image53.png "開啟網站管理頁面")</span><span class="sxs-lookup"><span data-stu-id="abdb3-767">![Opening the web site management pages](aspnet-mvc-4-fundamentals/_static/image53.png "Opening the web site management pages")</span></span>

    <span data-ttu-id="abdb3-768">*開啟網站管理頁面*</span><span class="sxs-lookup"><span data-stu-id="abdb3-768">*Opening the Web Site management pages*</span></span>
7. <span data-ttu-id="abdb3-769">在**儀表板**頁面的 **快速概覽**區段中，按一下**下載發行設定檔**連結。</span><span class="sxs-lookup"><span data-stu-id="abdb3-769">In the **Dashboard** page, under the **quick glance** section, click the **Download publish profile** link.</span></span>

    > [!NOTE]
    > <span data-ttu-id="abdb3-770">*發行設定檔*包含所有 web 應用程式發行至 Windows Azure 網站的每個已啟用的發行方法所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="abdb3-770">The *publish profile* contains all of the information required to publish a web application to a Windows Azure website for each enabled publication method.</span></span> <span data-ttu-id="abdb3-771">發行設定檔包含 Url、 使用者認證和資料庫連接，並對每個端點已啟用的發行集的方法進行驗證所需的字串。</span><span class="sxs-lookup"><span data-stu-id="abdb3-771">The publish profile contains the URLs, user credentials and database strings required to connect to and authenticate against each of the endpoints for which a publication method is enabled.</span></span> <span data-ttu-id="abdb3-772">**Microsoft WebMatrix 2**， **Microsoft Visual Studio Express for Web**和**Microsoft Visual Studio 2012**支援讀取發行設定檔自動將這些程式的組態web 應用程式發行至 Windows Azure 網站。</span><span class="sxs-lookup"><span data-stu-id="abdb3-772">**Microsoft WebMatrix 2**, **Microsoft Visual Studio Express for Web** and **Microsoft Visual Studio 2012** support reading publish profiles to automate configuration of these programs for publishing web applications to Windows Azure websites.</span></span>

    <span data-ttu-id="abdb3-773">![下載網站發行設定檔](aspnet-mvc-4-fundamentals/_static/image54.png "下載網站發行設定檔")</span><span class="sxs-lookup"><span data-stu-id="abdb3-773">![Downloading the web site publish profile](aspnet-mvc-4-fundamentals/_static/image54.png "Downloading the web site publish profile")</span></span>

    <span data-ttu-id="abdb3-774">*下載網站發行設定檔*</span><span class="sxs-lookup"><span data-stu-id="abdb3-774">*Downloading the Web Site publish profile*</span></span>
8. <span data-ttu-id="abdb3-775">下載發行設定檔至已知位置。</span><span class="sxs-lookup"><span data-stu-id="abdb3-775">Download the publish profile file to a known location.</span></span> <span data-ttu-id="abdb3-776">進一步在這個練習中，您會看到如何使用這個檔案從 Visual Studio 將 web 應用程式至 Windows Azure 網站發行。</span><span class="sxs-lookup"><span data-stu-id="abdb3-776">Further in this exercise you will see how to use this file to publish a web application to a Windows Azure Web Sites from Visual Studio.</span></span>

    <span data-ttu-id="abdb3-777">![儲存發行設定檔](aspnet-mvc-4-fundamentals/_static/image55.png "儲存發行設定檔")</span><span class="sxs-lookup"><span data-stu-id="abdb3-777">![Saving the publish profile file](aspnet-mvc-4-fundamentals/_static/image55.png "Saving the publish profile")</span></span>

    <span data-ttu-id="abdb3-778">*儲存發行設定檔*</span><span class="sxs-lookup"><span data-stu-id="abdb3-778">*Saving the publish profile file*</span></span>

<a id="ApxBTask2"></a>

<a id="Task_2_-_Configuring_the_Database_Server"></a>
#### <a name="task-2---configuring-the-database-server"></a><span data-ttu-id="abdb3-779">工作 2-設定資料庫伺服器</span><span class="sxs-lookup"><span data-stu-id="abdb3-779">Task 2 - Configuring the Database Server</span></span>

<span data-ttu-id="abdb3-780">如果您的應用程式會使用 SQL Server 資料庫，您必須建立 SQL Database 伺服器。</span><span class="sxs-lookup"><span data-stu-id="abdb3-780">If your application makes use of SQL Server databases you will need to create a SQL Database server.</span></span> <span data-ttu-id="abdb3-781">如果您想要部署簡單的應用程式不會使用 SQL Server，您可能會略過這項工作。</span><span class="sxs-lookup"><span data-stu-id="abdb3-781">If you want to deploy a simple application that does not use SQL Server you might skip this task.</span></span>

1. <span data-ttu-id="abdb3-782">您將需要 SQL Database 伺服器來儲存應用程式資料庫。</span><span class="sxs-lookup"><span data-stu-id="abdb3-782">You will need a SQL Database server for storing the application database.</span></span> <span data-ttu-id="abdb3-783">您可以從您的訂用帳戶，在 Windows Azure 管理入口網站中檢視 SQL Database 伺服器**Sql 資料庫** | **伺服器** | **伺服器儀表板**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-783">You can view the SQL Database servers from your subscription in the Windows Azure Management portal at **Sql Databases** | **Servers** | **Server's Dashboard**.</span></span> <span data-ttu-id="abdb3-784">如果您沒有建立伺服器，您可以建立一個使用**新增**命令列上的按鈕。</span><span class="sxs-lookup"><span data-stu-id="abdb3-784">If you do not have a server created, you can create one using the **Add** button on the command bar.</span></span> <span data-ttu-id="abdb3-785">請注意**伺服器名稱和 URL、 系統管理員身分登入名稱和密碼**，因為您將在下一個工作中使用它們。</span><span class="sxs-lookup"><span data-stu-id="abdb3-785">Take note of the **server name and URL, administrator login name and password**, as you will use them in the next tasks.</span></span> <span data-ttu-id="abdb3-786">並未建立資料庫，因為它會在後續階段中建立。</span><span class="sxs-lookup"><span data-stu-id="abdb3-786">Do not create the database yet, as it will be created in a later stage.</span></span>

    <span data-ttu-id="abdb3-787">![SQL Database 伺服器儀表板](aspnet-mvc-4-fundamentals/_static/image56.png "SQL Database 伺服器儀表板")</span><span class="sxs-lookup"><span data-stu-id="abdb3-787">![SQL Database Server Dashboard](aspnet-mvc-4-fundamentals/_static/image56.png "SQL Database Server Dashboard")</span></span>

    <span data-ttu-id="abdb3-788">*SQL Database 伺服器儀表板*</span><span class="sxs-lookup"><span data-stu-id="abdb3-788">*SQL Database Server Dashboard*</span></span>
2. <span data-ttu-id="abdb3-789">下一項工作在您將測試資料庫連接，從 Visual Studio，因此您需要在伺服器的清單中包含您的本機 IP 位址**允許的 IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-789">In the next task you will test the database connection from Visual Studio, for that reason you need to include your local IP address in the server's list of **Allowed IP Addresses**.</span></span> <span data-ttu-id="abdb3-790">若要這樣做，請按一下**設定**，選取 [IP 位址從**目前的用戶端 IP 位址**並將它貼上**起始 IP 位址**和**結束 IP 位址**文字方塊，然後按一下![add-client-ip-address-ok-button](aspnet-mvc-4-fundamentals/_static/image57.png) ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="abdb3-790">To do that, click **Configure**, select the IP address from **Current Client IP Address** and paste it on the **Start IP Address** and **End IP Address** text boxes and click the ![add-client-ip-address-ok-button](aspnet-mvc-4-fundamentals/_static/image57.png) button.</span></span>

    ![加入用戶端 IP 位址](aspnet-mvc-4-fundamentals/_static/image58.png)

    <span data-ttu-id="abdb3-792">*加入用戶端 IP 位址*</span><span class="sxs-lookup"><span data-stu-id="abdb3-792">*Adding Client IP Address*</span></span>
3. <span data-ttu-id="abdb3-793">一次**用戶端 IP 位址**新增至允許的 IP 位址清單中，按一下**儲存**來確認變更。</span><span class="sxs-lookup"><span data-stu-id="abdb3-793">Once the **Client IP Address** is added to the allowed IP addresses list, click on **Save** to confirm the changes.</span></span>

    ![確認變更](aspnet-mvc-4-fundamentals/_static/image59.png)

    <span data-ttu-id="abdb3-795">*確認變更*</span><span class="sxs-lookup"><span data-stu-id="abdb3-795">*Confirm Changes*</span></span>

<a id="ApxBTask3"></a>

<a id="Task_3_-_Publishing_an_ASPNET_MVC_4_Application_using_Web_Deploy"></a>
#### <a name="task-3---publishing-an-aspnet-mvc-4-application-using-web-deploy"></a><span data-ttu-id="abdb3-796">工作 3-發行 ASP.NET MVC 4 應用程式使用 Web Deploy</span><span class="sxs-lookup"><span data-stu-id="abdb3-796">Task 3 - Publishing an ASP.NET MVC 4 Application using Web Deploy</span></span>

1. <span data-ttu-id="abdb3-797">返回至 ASP.NET MVC 4 方案。</span><span class="sxs-lookup"><span data-stu-id="abdb3-797">Go back to the ASP.NET MVC 4 solution.</span></span> <span data-ttu-id="abdb3-798">在**方案總管 中**，以滑鼠右鍵按一下網站專案，然後選取**發行**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-798">In the **Solution Explorer**, right-click the web site project and select **Publish**.</span></span>

    <span data-ttu-id="abdb3-799">![發行應用程式](aspnet-mvc-4-fundamentals/_static/image60.png "發行應用程式")</span><span class="sxs-lookup"><span data-stu-id="abdb3-799">![Publishing the Application](aspnet-mvc-4-fundamentals/_static/image60.png "Publishing the Application")</span></span>

    <span data-ttu-id="abdb3-800">*發行網站*</span><span class="sxs-lookup"><span data-stu-id="abdb3-800">*Publishing the web site*</span></span>
2. <span data-ttu-id="abdb3-801">匯入發行設定檔儲存在第一項工作中。</span><span class="sxs-lookup"><span data-stu-id="abdb3-801">Import the publish profile you saved in the first task.</span></span>

    <span data-ttu-id="abdb3-802">![匯入發行設定檔](aspnet-mvc-4-fundamentals/_static/image61.png "匯入發行設定檔")</span><span class="sxs-lookup"><span data-stu-id="abdb3-802">![Importing the publish profile](aspnet-mvc-4-fundamentals/_static/image61.png "Importing the publish profile")</span></span>

    <span data-ttu-id="abdb3-803">*匯入發行設定檔*</span><span class="sxs-lookup"><span data-stu-id="abdb3-803">*Importing publish profile*</span></span>
3. <span data-ttu-id="abdb3-804">按一下**驗證連線**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-804">Click **Validate Connection**.</span></span> <span data-ttu-id="abdb3-805">驗證完成後按一下**下一步**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-805">Once Validation is complete click **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="abdb3-806">一旦您看到 [驗證連線] 按鈕旁邊會出現綠色核取記號完成驗證。</span><span class="sxs-lookup"><span data-stu-id="abdb3-806">Validation is complete once you see a green checkmark appear next to the Validate Connection button.</span></span>

    <span data-ttu-id="abdb3-807">![驗證連線](aspnet-mvc-4-fundamentals/_static/image62.png "驗證連線")</span><span class="sxs-lookup"><span data-stu-id="abdb3-807">![Validating connection](aspnet-mvc-4-fundamentals/_static/image62.png "Validating connection")</span></span>

    <span data-ttu-id="abdb3-808">*驗證連接*</span><span class="sxs-lookup"><span data-stu-id="abdb3-808">*Validating connection*</span></span>
4. <span data-ttu-id="abdb3-809">在**設定**頁面的 **資料庫**區段中，按一下您的資料庫連接文字方塊旁邊的按鈕 (也就是**DefaultConnection**)。</span><span class="sxs-lookup"><span data-stu-id="abdb3-809">In the **Settings** page, under the **Databases** section, click the button next to your database connection's textbox (i.e. **DefaultConnection**).</span></span>

    <span data-ttu-id="abdb3-810">![Web 部署設定](aspnet-mvc-4-fundamentals/_static/image63.png "Web 部署設定")</span><span class="sxs-lookup"><span data-stu-id="abdb3-810">![Web deploy configuration](aspnet-mvc-4-fundamentals/_static/image63.png "Web deploy configuration")</span></span>

    <span data-ttu-id="abdb3-811">*Web 部署設定*</span><span class="sxs-lookup"><span data-stu-id="abdb3-811">*Web deploy configuration*</span></span>
5. <span data-ttu-id="abdb3-812">設定資料庫連接，如下所示：</span><span class="sxs-lookup"><span data-stu-id="abdb3-812">Configure the database connection as follows:</span></span>

    - <span data-ttu-id="abdb3-813">在**伺服器名稱**您 SQL Database 伺服器 URL 使用下列方法類型*tcp:*前置詞。</span><span class="sxs-lookup"><span data-stu-id="abdb3-813">In the **Server name** type your SQL Database server URL using the *tcp:* prefix.</span></span>
    - <span data-ttu-id="abdb3-814">在**使用者名**輸入您的伺服器系統管理員身分登入名稱。</span><span class="sxs-lookup"><span data-stu-id="abdb3-814">In **User name** type your server administrator login name.</span></span>
    - <span data-ttu-id="abdb3-815">在**密碼**輸入伺服器系統管理員身分登入密碼。</span><span class="sxs-lookup"><span data-stu-id="abdb3-815">In **Password** type your server administrator login password.</span></span>
    - <span data-ttu-id="abdb3-816">輸入新的資料庫名稱，例如： *MVC4SampleDB*。</span><span class="sxs-lookup"><span data-stu-id="abdb3-816">Type a new database name, for example: *MVC4SampleDB*.</span></span>

    <span data-ttu-id="abdb3-817">![設定目的地連接字串](aspnet-mvc-4-fundamentals/_static/image64.png "設定目的地連接字串")</span><span class="sxs-lookup"><span data-stu-id="abdb3-817">![Configuring destination connection string](aspnet-mvc-4-fundamentals/_static/image64.png "Configuring destination connection string")</span></span>

    <span data-ttu-id="abdb3-818">*設定目的地連接字串*</span><span class="sxs-lookup"><span data-stu-id="abdb3-818">*Configuring destination connection string*</span></span>
6. <span data-ttu-id="abdb3-819">然後按一下 [確定]。 </span><span class="sxs-lookup"><span data-stu-id="abdb3-819">Then click **OK**.</span></span> <span data-ttu-id="abdb3-820">當系統提示您建立資料庫依序按一下**是**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-820">When prompted to create the database click **Yes**.</span></span>

    <span data-ttu-id="abdb3-821">![建立資料庫](aspnet-mvc-4-fundamentals/_static/image65.png "建立的資料庫字串")</span><span class="sxs-lookup"><span data-stu-id="abdb3-821">![Creating the database](aspnet-mvc-4-fundamentals/_static/image65.png "Creating the database string")</span></span>

    <span data-ttu-id="abdb3-822">*建立資料庫*</span><span class="sxs-lookup"><span data-stu-id="abdb3-822">*Creating the database*</span></span>
7. <span data-ttu-id="abdb3-823">您將用來連接到在 Windows Azure SQL Database 的連接字串會顯示在預設連接文字方塊中。</span><span class="sxs-lookup"><span data-stu-id="abdb3-823">The connection string you will use to connect to SQL Database in Windows Azure is shown within Default Connection textbox.</span></span> <span data-ttu-id="abdb3-824">然後按 [下一步] 。</span><span class="sxs-lookup"><span data-stu-id="abdb3-824">Then click **Next**.</span></span>

    <span data-ttu-id="abdb3-825">![連接字串指向 SQL Database](aspnet-mvc-4-fundamentals/_static/image66.png "連接字串指向 SQL 資料庫")</span><span class="sxs-lookup"><span data-stu-id="abdb3-825">![Connection string pointing to SQL Database](aspnet-mvc-4-fundamentals/_static/image66.png "Connection string pointing to SQL Database")</span></span>

    <span data-ttu-id="abdb3-826">*連接字串指向 SQL 資料庫*</span><span class="sxs-lookup"><span data-stu-id="abdb3-826">*Connection string pointing to SQL Database*</span></span>
8. <span data-ttu-id="abdb3-827">在**預覽**頁面上，按一下**發行**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-827">In the **Preview** page, click **Publish**.</span></span>

    <span data-ttu-id="abdb3-828">![Web 應用程式發行](aspnet-mvc-4-fundamentals/_static/image67.png "發行 web 應用程式")</span><span class="sxs-lookup"><span data-stu-id="abdb3-828">![Publishing the web application](aspnet-mvc-4-fundamentals/_static/image67.png "Publishing the web application")</span></span>

    <span data-ttu-id="abdb3-829">*發行 web 應用程式*</span><span class="sxs-lookup"><span data-stu-id="abdb3-829">*Publishing the web application*</span></span>
9. <span data-ttu-id="abdb3-830">一旦在發佈程序完成時，預設瀏覽器會開啟已發行的網站。</span><span class="sxs-lookup"><span data-stu-id="abdb3-830">Once the publishing process finishes, your default browser will open the published web site.</span></span>

    <span data-ttu-id="abdb3-831">![應用程式發行至 Windows Azure](aspnet-mvc-4-fundamentals/_static/image68.png "應用程式發行至 Windows Azure")</span><span class="sxs-lookup"><span data-stu-id="abdb3-831">![Application published to Windows Azure](aspnet-mvc-4-fundamentals/_static/image68.png "Application published to Windows Azure")</span></span>

    <span data-ttu-id="abdb3-832">*應用程式發行至 Windows Azure*</span><span class="sxs-lookup"><span data-stu-id="abdb3-832">*Application published to Windows Azure*</span></span>

<a id="AppendixC"></a>

<a id="Appendix_C_Using_Code_Snippets"></a>
## <a name="appendix-c-using-code-snippets"></a><span data-ttu-id="abdb3-833">附錄 c： 使用程式碼片段</span><span class="sxs-lookup"><span data-stu-id="abdb3-833">Appendix C: Using Code Snippets</span></span>

<span data-ttu-id="abdb3-834">程式碼片段，您會有您需要在您可以的所有程式碼。</span><span class="sxs-lookup"><span data-stu-id="abdb3-834">With code snippets, you have all the code you need at your fingertips.</span></span> <span data-ttu-id="abdb3-835">實驗室文件會告訴您完全時您可以使用它們，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="abdb3-835">The lab document will tell you exactly when you can use them, as shown in the following figure.</span></span>

<span data-ttu-id="abdb3-836">![若要將程式碼插入您的專案中使用 Visual Studio 程式碼片段](aspnet-mvc-4-fundamentals/_static/image69.png "使用 Visual Studio 程式碼片段，將程式碼插入您的專案")</span><span class="sxs-lookup"><span data-stu-id="abdb3-836">![Using Visual Studio code snippets to insert code into your project](aspnet-mvc-4-fundamentals/_static/image69.png "Using Visual Studio code snippets to insert code into your project")</span></span>

<span data-ttu-id="abdb3-837">*若要將程式碼插入您的專案中使用 Visual Studio 程式碼片段*</span><span class="sxs-lookup"><span data-stu-id="abdb3-837">*Using Visual Studio code snippets to insert code into your project*</span></span>

<span data-ttu-id="abdb3-838">***若要加入的程式碼片段，使用鍵盤 （僅限 C#)***</span><span class="sxs-lookup"><span data-stu-id="abdb3-838">***To add a code snippet using the keyboard (C# only)***</span></span>

1. <span data-ttu-id="abdb3-839">將游標放在您想要插入的程式碼。</span><span class="sxs-lookup"><span data-stu-id="abdb3-839">Place the cursor where you would like to insert the code.</span></span>
2. <span data-ttu-id="abdb3-840">開始鍵入片段名稱 （不含空格或連字號）。</span><span class="sxs-lookup"><span data-stu-id="abdb3-840">Start typing the snippet name (without spaces or hyphens).</span></span>
3. <span data-ttu-id="abdb3-841">觀察 IntelliSense 會顯示比對程式碼片段的名稱。</span><span class="sxs-lookup"><span data-stu-id="abdb3-841">Watch as IntelliSense displays matching snippets' names.</span></span>
4. <span data-ttu-id="abdb3-842">選取正確的程式碼片段 （或直到選取整個程式碼片段名稱時，保留 輸入）。</span><span class="sxs-lookup"><span data-stu-id="abdb3-842">Select the correct snippet (or keep typing until the entire snippet's name is selected).</span></span>
5. <span data-ttu-id="abdb3-843">按下 Tab 鍵兩次的游標位置插入程式碼片段。</span><span class="sxs-lookup"><span data-stu-id="abdb3-843">Press the Tab key twice to insert the snippet at the cursor location.</span></span>

<span data-ttu-id="abdb3-844">![開始輸入程式碼片段名稱](aspnet-mvc-4-fundamentals/_static/image70.png "開始鍵入片段名稱")</span><span class="sxs-lookup"><span data-stu-id="abdb3-844">![Start typing the snippet name](aspnet-mvc-4-fundamentals/_static/image70.png "Start typing the snippet name")</span></span>

<span data-ttu-id="abdb3-845">*開始輸入程式碼片段名稱*</span><span class="sxs-lookup"><span data-stu-id="abdb3-845">*Start typing the snippet name*</span></span>

<span data-ttu-id="abdb3-846">![按 Tab 鍵選取反白顯示的程式碼片段](aspnet-mvc-4-fundamentals/_static/image71.png "按 Tab 鍵以選取反白顯示的程式碼片段")</span><span class="sxs-lookup"><span data-stu-id="abdb3-846">![Press Tab to select the highlighted snippet](aspnet-mvc-4-fundamentals/_static/image71.png "Press Tab to select the highlighted snippet")</span></span>

<span data-ttu-id="abdb3-847">*按 Tab 鍵選取反白顯示的程式碼片段*</span><span class="sxs-lookup"><span data-stu-id="abdb3-847">*Press Tab to select the highlighted snippet*</span></span>

<span data-ttu-id="abdb3-848">![按 Tab 鍵一次程式碼片段就會擴展](aspnet-mvc-4-fundamentals/_static/image72.png "按 Tab 鍵一次程式碼片段就會擴展")</span><span class="sxs-lookup"><span data-stu-id="abdb3-848">![Press Tab again and the snippet will expand](aspnet-mvc-4-fundamentals/_static/image72.png "Press Tab again and the snippet will expand")</span></span>

<span data-ttu-id="abdb3-849">*按 Tab 鍵一次程式碼片段就會擴展*</span><span class="sxs-lookup"><span data-stu-id="abdb3-849">*Press Tab again and the snippet will expand*</span></span>

<span data-ttu-id="abdb3-850">***若要加入的程式碼片段，使用滑鼠 （C#、 Visual Basic 和 XML）*** 1。</span><span class="sxs-lookup"><span data-stu-id="abdb3-850">***To add a code snippet using the mouse (C#, Visual Basic and XML)*** 1.</span></span> <span data-ttu-id="abdb3-851">以滑鼠右鍵按一下您要插入程式碼片段。</span><span class="sxs-lookup"><span data-stu-id="abdb3-851">Right-click where you want to insert the code snippet.</span></span>

1. <span data-ttu-id="abdb3-852">選取**插入程式碼片段**後面**我的程式碼片段**。</span><span class="sxs-lookup"><span data-stu-id="abdb3-852">Select **Insert Snippet** followed by **My Code Snippets**.</span></span>
2. <span data-ttu-id="abdb3-853">透過在按一下挑選清單中，從相關的程式碼片段。</span><span class="sxs-lookup"><span data-stu-id="abdb3-853">Pick the relevant snippet from the list, by clicking on it.</span></span>

<span data-ttu-id="abdb3-854">![以滑鼠右鍵按一下您要插入程式碼片段，然後選取 插入程式碼片段](aspnet-mvc-4-fundamentals/_static/image73.png "以滑鼠右鍵按一下您要插入程式碼片段，然後選取 插入程式碼片段")</span><span class="sxs-lookup"><span data-stu-id="abdb3-854">![Right-click where you want to insert the code snippet and select Insert Snippet](aspnet-mvc-4-fundamentals/_static/image73.png "Right-click where you want to insert the code snippet and select Insert Snippet")</span></span>

<span data-ttu-id="abdb3-855">*以滑鼠右鍵按一下您要插入程式碼片段，然後選取 插入程式碼片段*</span><span class="sxs-lookup"><span data-stu-id="abdb3-855">*Right-click where you want to insert the code snippet and select Insert Snippet*</span></span>

<span data-ttu-id="abdb3-856">![透過在按一下挑選清單中，從相關的程式碼片段](aspnet-mvc-4-fundamentals/_static/image74.png "上它即可挑選清單中，從相關的程式碼片段")</span><span class="sxs-lookup"><span data-stu-id="abdb3-856">![Pick the relevant snippet from the list, by clicking on it](aspnet-mvc-4-fundamentals/_static/image74.png "Pick the relevant snippet from the list, by clicking on it")</span></span>

<span data-ttu-id="abdb3-857">*透過在按一下挑選清單中，從相關的程式碼片段*</span><span class="sxs-lookup"><span data-stu-id="abdb3-857">*Pick the relevant snippet from the list, by clicking on it*</span></span>