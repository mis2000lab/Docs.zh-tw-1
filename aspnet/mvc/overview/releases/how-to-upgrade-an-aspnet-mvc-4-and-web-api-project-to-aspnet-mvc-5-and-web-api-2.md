---
uid: mvc/overview/releases/how-to-upgrade-an-aspnet-mvc-4-and-web-api-project-to-aspnet-mvc-5-and-web-api-2
title: "如何升級 ASP.NET MVC 4 和 Web API 專案，以 ASP.NET MVC 5 和 Web API 2 |Microsoft 文件"
author: Rick-Anderson
description: "ASP.NET MVC 5 和 Web API 2 將新功能，包括路由屬性、 驗證篩選條件，以及執行更多的主機。"
ms.author: aspnetcontent
manager: wpickett
ms.date: 10/17/2013
ms.topic: article
ms.assetid: db0d02d9-58e8-4a0b-8d7d-b8df8ea97b88
ms.technology: dotnet-mvc
ms.prod: .net-framework
msc.legacyurl: /mvc/overview/releases/how-to-upgrade-an-aspnet-mvc-4-and-web-api-project-to-aspnet-mvc-5-and-web-api-2
msc.type: authoredcontent
ms.openlocfilehash: 05a3189cf105d1230b96e90b46ea5ab60fef1bf1
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2017
---
<a name="how-to-upgrade-an-aspnet-mvc-4-and-web-api-project-to-aspnet-mvc-5-and-web-api-2"></a><span data-ttu-id="ff704-103">如何將 ASP.NET MVC 4 和 Web API 專案升級至 ASP.NET MVC 5 和 Web API 2</span><span class="sxs-lookup"><span data-stu-id="ff704-103">How to Upgrade an ASP.NET MVC 4 and Web API Project to ASP.NET MVC 5 and Web API 2</span></span>
====================
<span data-ttu-id="ff704-104">由[Rick Anderson](https://github.com/Rick-Anderson)</span><span class="sxs-lookup"><span data-stu-id="ff704-104">by [Rick Anderson](https://github.com/Rick-Anderson)</span></span>

> <span data-ttu-id="ff704-105">ASP.NET MVC 5 和 Web API 2 將新功能，包括路由屬性、 驗證篩選條件，以及執行更多的主機。</span><span class="sxs-lookup"><span data-stu-id="ff704-105">ASP.NET MVC 5 and Web API 2 bring a host of new features, including attribute routing, authentication filters, and much more.</span></span> <span data-ttu-id="ff704-106">請參閱[https://www.asp.net/vnext](https://www.asp.net/core)如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ff704-106">See [https://www.asp.net/vnext](https://www.asp.net/core) for more details.</span></span>
> 
> <span data-ttu-id="ff704-107">本逐步解說會引導您升級為最新版本的應用程式所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="ff704-107">This walkthrough will guide you with the steps required to upgrade your application to the latest version.</span></span>  
> 
> > [!NOTE]
> > <span data-ttu-id="ff704-108">請參閱[ASP.NET 及 Web Tools for Visual Studio 2013 版本資訊](../../../visual-studio/overview/2013/release-notes.md)的重大變更到下一個版本 MVC 4 和 Web API 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ff704-108">Please see [ASP.NET and Web Tools for Visual Studio 2013 Release Notes](../../../visual-studio/overview/2013/release-notes.md) for information on breaking changes from MVC 4 and Web API to the next version.</span></span>
> 
>   
> 
> <span data-ttu-id="ff704-109">本文撰寫 Youngjune 香港和 Rick Anderson ( [ @RickAndMSFT ](https://twitter.com/#!/RickAndMSFT) )</span><span class="sxs-lookup"><span data-stu-id="ff704-109">This article was written by Youngjune Hong and Rick Anderson ( [@RickAndMSFT](https://twitter.com/#!/RickAndMSFT) )</span></span>


## <a name="upgrade-steps"></a><span data-ttu-id="ff704-110">升級步驟</span><span class="sxs-lookup"><span data-stu-id="ff704-110">Upgrade Steps</span></span>

1. <span data-ttu-id="ff704-111">備份您的專案。</span><span class="sxs-lookup"><span data-stu-id="ff704-111">Backup your project.</span></span> <span data-ttu-id="ff704-112">本逐步解說將會要求您對您的專案檔、 封裝組態和 web.config 檔案中的變更。</span><span class="sxs-lookup"><span data-stu-id="ff704-112">This walkthrough will require you to make changes to your project file, package configuration, and web.config files.</span></span>
2. <span data-ttu-id="ff704-113">在 global.asax 中, 升級從 Web API Web API 2，變更：</span><span class="sxs-lookup"><span data-stu-id="ff704-113">For upgrading from Web API to Web API 2, in global.asax, change:</span></span>

    [!code-csharp[Main](how-to-upgrade-an-aspnet-mvc-4-and-web-api-project-to-aspnet-mvc-5-and-web-api-2/samples/sample1.cs)]

 <span data-ttu-id="ff704-114">設為</span><span class="sxs-lookup"><span data-stu-id="ff704-114">to</span></span>

    [!code-csharp[Main](how-to-upgrade-an-aspnet-mvc-4-and-web-api-project-to-aspnet-mvc-5-and-web-api-2/samples/sample2.cs)]
3. <span data-ttu-id="ff704-115">請確定您的專案使用的所有封裝都都與 MVC 5 和 Web API 2 相容。</span><span class="sxs-lookup"><span data-stu-id="ff704-115">Make sure all the packages that your projects use are compatible with MVC 5 and Web API 2.</span></span> <span data-ttu-id="ff704-116">下列表格顯示 MVC 4 和 Web API 相關封裝比需要變更。</span><span class="sxs-lookup"><span data-stu-id="ff704-116">The following table shows the MVC 4 and Web API related packages than need to be changed.</span></span> <span data-ttu-id="ff704-117">如果您有相依於其中一個下面所列封裝的封裝，請連絡發行者以取得與 MVC 5 和 Web API 2 相容的較新版本。</span><span class="sxs-lookup"><span data-stu-id="ff704-117">If you have a package that is dependent on one of the packages listed below, please contact the publishers to get the newer versions that are compatible with MVC 5 and Web API 2.</span></span> <span data-ttu-id="ff704-118">如果您有這些封裝的原始程式碼，則應該使用新的組件的 MVC 5 和 Web API 2 重新編譯它們。</span><span class="sxs-lookup"><span data-stu-id="ff704-118">If you have the source code for those packages, you should recompile them with the new assemblies of MVC 5 and Web API 2.</span></span>   

    | <span data-ttu-id="ff704-119">**封裝識別碼**</span><span class="sxs-lookup"><span data-stu-id="ff704-119">**Package Id**</span></span> | <span data-ttu-id="ff704-120">**舊的版本**</span><span class="sxs-lookup"><span data-stu-id="ff704-120">**Old version**</span></span> | <span data-ttu-id="ff704-121">**新的版本**</span><span class="sxs-lookup"><span data-stu-id="ff704-121">**New version**</span></span> |
    | --- | --- | --- |
    | <span data-ttu-id="ff704-122">Microsoft.AspNet.Razor</span><span class="sxs-lookup"><span data-stu-id="ff704-122">Microsoft.AspNet.Razor</span></span> | <span data-ttu-id="ff704-123">2.0.x.x</span><span class="sxs-lookup"><span data-stu-id="ff704-123">2.0.x.x</span></span> | <span data-ttu-id="ff704-124">3.0.0</span><span class="sxs-lookup"><span data-stu-id="ff704-124">3.0.0</span></span> |
    | <span data-ttu-id="ff704-125">Microsoft.AspNet.WebPages</span><span class="sxs-lookup"><span data-stu-id="ff704-125">Microsoft.AspNet.WebPages</span></span> | <span data-ttu-id="ff704-126">2.0.x.x</span><span class="sxs-lookup"><span data-stu-id="ff704-126">2.0.x.x</span></span> | <span data-ttu-id="ff704-127">3.0.0</span><span class="sxs-lookup"><span data-stu-id="ff704-127">3.0.0</span></span> |
    | <span data-ttu-id="ff704-128">Microsoft.AspNet.WebPages.WebData</span><span class="sxs-lookup"><span data-stu-id="ff704-128">Microsoft.AspNet.WebPages.WebData</span></span> | <span data-ttu-id="ff704-129">2.0.x.x</span><span class="sxs-lookup"><span data-stu-id="ff704-129">2.0.x.x</span></span> | <span data-ttu-id="ff704-130">3.0.0</span><span class="sxs-lookup"><span data-stu-id="ff704-130">3.0.0</span></span> |
    | <span data-ttu-id="ff704-131">Microsoft.AspNet.WebPages.OAuth</span><span class="sxs-lookup"><span data-stu-id="ff704-131">Microsoft.AspNet.WebPages.OAuth</span></span> | <span data-ttu-id="ff704-132">2.0.x.x</span><span class="sxs-lookup"><span data-stu-id="ff704-132">2.0.x.x</span></span> | <span data-ttu-id="ff704-133">3.0.0</span><span class="sxs-lookup"><span data-stu-id="ff704-133">3.0.0</span></span> |
    | <span data-ttu-id="ff704-134">Microsoft.AspNet.Mvc</span><span class="sxs-lookup"><span data-stu-id="ff704-134">Microsoft.AspNet.Mvc</span></span> | <span data-ttu-id="ff704-135">4.0.x.x</span><span class="sxs-lookup"><span data-stu-id="ff704-135">4.0.x.x</span></span> | <span data-ttu-id="ff704-136">5.0.0</span><span class="sxs-lookup"><span data-stu-id="ff704-136">5.0.0</span></span> |
    | <span data-ttu-id="ff704-137">Microsoft.AspNet.Mvc.Facebook</span><span class="sxs-lookup"><span data-stu-id="ff704-137">Microsoft.AspNet.Mvc.Facebook</span></span> | <span data-ttu-id="ff704-138">4.0.x.x</span><span class="sxs-lookup"><span data-stu-id="ff704-138">4.0.x.x</span></span> | <span data-ttu-id="ff704-139">5.0.0</span><span class="sxs-lookup"><span data-stu-id="ff704-139">5.0.0</span></span> |
    | <span data-ttu-id="ff704-140">Microsoft.AspNet.WebApi.Core</span><span class="sxs-lookup"><span data-stu-id="ff704-140">Microsoft.AspNet.WebApi.Core</span></span> | <span data-ttu-id="ff704-141">4.0.x.x</span><span class="sxs-lookup"><span data-stu-id="ff704-141">4.0.x.x</span></span> | <span data-ttu-id="ff704-142">5.0.0</span><span class="sxs-lookup"><span data-stu-id="ff704-142">5.0.0</span></span> |
    | <span data-ttu-id="ff704-143">Microsoft.AspNet.WebApi.SelfHost</span><span class="sxs-lookup"><span data-stu-id="ff704-143">Microsoft.AspNet.WebApi.SelfHost</span></span> | <span data-ttu-id="ff704-144">4.0.x.x</span><span class="sxs-lookup"><span data-stu-id="ff704-144">4.0.x.x</span></span> | <span data-ttu-id="ff704-145">5.0.0</span><span class="sxs-lookup"><span data-stu-id="ff704-145">5.0.0</span></span> |
    | <span data-ttu-id="ff704-146">Microsoft.AspNet.WebApi.Client</span><span class="sxs-lookup"><span data-stu-id="ff704-146">Microsoft.AspNet.WebApi.Client</span></span> | <span data-ttu-id="ff704-147">4.0.x.x</span><span class="sxs-lookup"><span data-stu-id="ff704-147">4.0.x.x</span></span> | <span data-ttu-id="ff704-148">5.0.0</span><span class="sxs-lookup"><span data-stu-id="ff704-148">5.0.0</span></span> |
    | <span data-ttu-id="ff704-149">用於 Microsoft.AspNet.WebApi.OData</span><span class="sxs-lookup"><span data-stu-id="ff704-149">Microsoft.AspNet.WebApi.OData</span></span> | <span data-ttu-id="ff704-150">4.0.x.x</span><span class="sxs-lookup"><span data-stu-id="ff704-150">4.0.x.x</span></span> | <span data-ttu-id="ff704-151">5.0.0</span><span class="sxs-lookup"><span data-stu-id="ff704-151">5.0.0</span></span> |
    | <span data-ttu-id="ff704-152">Microsoft.AspNet.WebApi</span><span class="sxs-lookup"><span data-stu-id="ff704-152">Microsoft.AspNet.WebApi</span></span> | <span data-ttu-id="ff704-153">4.0.x.x</span><span class="sxs-lookup"><span data-stu-id="ff704-153">4.0.x.x</span></span> | <span data-ttu-id="ff704-154">5.0.0</span><span class="sxs-lookup"><span data-stu-id="ff704-154">5.0.0</span></span> |
    | <span data-ttu-id="ff704-155">Microsoft.AspNet.WebApi.WebHost</span><span class="sxs-lookup"><span data-stu-id="ff704-155">Microsoft.AspNet.WebApi.WebHost</span></span> | <span data-ttu-id="ff704-156">4.0.x.x</span><span class="sxs-lookup"><span data-stu-id="ff704-156">4.0.x.x</span></span> | <span data-ttu-id="ff704-157">5.0.0</span><span class="sxs-lookup"><span data-stu-id="ff704-157">5.0.0</span></span> |
    | <span data-ttu-id="ff704-158">用於 Microsoft.AspNet.WebApi.Tracing</span><span class="sxs-lookup"><span data-stu-id="ff704-158">Microsoft.AspNet.WebApi.Tracing</span></span> | <span data-ttu-id="ff704-159">4.0.x.x</span><span class="sxs-lookup"><span data-stu-id="ff704-159">4.0.x.x</span></span> | <span data-ttu-id="ff704-160">5.0.0</span><span class="sxs-lookup"><span data-stu-id="ff704-160">5.0.0</span></span> |
    | <span data-ttu-id="ff704-161">Microsoft.AspNet.WebApi.HelpPage</span><span class="sxs-lookup"><span data-stu-id="ff704-161">Microsoft.AspNet.WebApi.HelpPage</span></span> | <span data-ttu-id="ff704-162">4.0.x.x</span><span class="sxs-lookup"><span data-stu-id="ff704-162">4.0.x.x</span></span> | <span data-ttu-id="ff704-163">5.0.0</span><span class="sxs-lookup"><span data-stu-id="ff704-163">5.0.0</span></span> |
    | <span data-ttu-id="ff704-164">Microsoft.Net.Http</span><span class="sxs-lookup"><span data-stu-id="ff704-164">Microsoft.Net.Http</span></span> | <span data-ttu-id="ff704-165">2.0.x 版。</span><span class="sxs-lookup"><span data-stu-id="ff704-165">2.0.x.</span></span> | <span data-ttu-id="ff704-166">2.2.x。</span><span class="sxs-lookup"><span data-stu-id="ff704-166">2.2.x.</span></span> |
    | <span data-ttu-id="ff704-167">Microsoft.Data.OData</span><span class="sxs-lookup"><span data-stu-id="ff704-167">Microsoft.Data.OData</span></span> | <span data-ttu-id="ff704-168">5.2.x</span><span class="sxs-lookup"><span data-stu-id="ff704-168">5.2.x</span></span> | <span data-ttu-id="ff704-169">5.6.x</span><span class="sxs-lookup"><span data-stu-id="ff704-169">5.6.x</span></span> |
    | <span data-ttu-id="ff704-170">System.Spatial</span><span class="sxs-lookup"><span data-stu-id="ff704-170">System.Spatial</span></span> | <span data-ttu-id="ff704-171">5.2.x</span><span class="sxs-lookup"><span data-stu-id="ff704-171">5.2.x</span></span> | <span data-ttu-id="ff704-172">5.6.x</span><span class="sxs-lookup"><span data-stu-id="ff704-172">5.6.x</span></span> |
    | <span data-ttu-id="ff704-173">Microsoft.Data.Edm</span><span class="sxs-lookup"><span data-stu-id="ff704-173">Microsoft.Data.Edm</span></span> | <span data-ttu-id="ff704-174">5.2.x</span><span class="sxs-lookup"><span data-stu-id="ff704-174">5.2.x</span></span> | <span data-ttu-id="ff704-175">5.6.x</span><span class="sxs-lookup"><span data-stu-id="ff704-175">5.6.x</span></span> |
    | <span data-ttu-id="ff704-176">Microsoft.AspNet.Mvc.FixedDisplayModes</span><span class="sxs-lookup"><span data-stu-id="ff704-176">Microsoft.AspNet.Mvc.FixedDisplayModes</span></span> | <span data-ttu-id="ff704-177">< o: p>< >< / o: p>< ></span><span class="sxs-lookup"><span data-stu-id="ff704-177"><o:p> </o:p></span></span> | <span data-ttu-id="ff704-178">已移除</span><span class="sxs-lookup"><span data-stu-id="ff704-178">Removed</span></span> |
    | <span data-ttu-id="ff704-179">Microsoft.AspNet.WebPages.Administration</span><span class="sxs-lookup"><span data-stu-id="ff704-179">Microsoft.AspNet.WebPages.Administration</span></span> | <span data-ttu-id="ff704-180">< o: p>< >< / o: p>< ></span><span class="sxs-lookup"><span data-stu-id="ff704-180"><o:p> </o:p></span></span> | <span data-ttu-id="ff704-181">已移除</span><span class="sxs-lookup"><span data-stu-id="ff704-181">Removed</span></span> |
    | <span data-ttu-id="ff704-182">Microsoft Web Helpers</span><span class="sxs-lookup"><span data-stu-id="ff704-182">Microsoft-Web-Helpers</span></span> | <span data-ttu-id="ff704-183">< o: p>< >< / o: p>< ></span><span class="sxs-lookup"><span data-stu-id="ff704-183"><o:p> </o:p></span></span> | <span data-ttu-id="ff704-184">Microsoft.AspNet.WebHelpers</span><span class="sxs-lookup"><span data-stu-id="ff704-184">Microsoft.AspNet.WebHelpers</span></span> |

    > [!NOTE]
    > <span data-ttu-id="ff704-185">Microsoft Web Helpers Microsoft.AspNet.WebHelpers 已取代。</span><span class="sxs-lookup"><span data-stu-id="ff704-185">Microsoft-Web-Helpers has been replaced with Microsoft.AspNet.WebHelpers.</span></span> <span data-ttu-id="ff704-186">您應該先移除舊的封裝，然後再安裝較新的封裝。</span><span class="sxs-lookup"><span data-stu-id="ff704-186">You should remove the old package first, and then install the newer package.</span></span>   
    >   
    > <span data-ttu-id="ff704-187">沒有跨版本之間的相容性主要 ASP.NET 封裝。</span><span class="sxs-lookup"><span data-stu-id="ff704-187">There is no cross version compatibility among major ASP.NET packages.</span></span> <span data-ttu-id="ff704-188">例如，MVC 5 是只使用 Razor 3 和 Razor 2 不相容。</span><span class="sxs-lookup"><span data-stu-id="ff704-188">For example, MVC 5 is compatible with only Razor 3, and not Razor 2.</span></span>
4. <span data-ttu-id="ff704-189">Visual Studio 2013 中開啟您的專案。</span><span class="sxs-lookup"><span data-stu-id="ff704-189">Open your project in Visual Studio 2013.</span></span>
5. <span data-ttu-id="ff704-190">移除任何已安裝下列 ASP.NET NuGet 套件。</span><span class="sxs-lookup"><span data-stu-id="ff704-190">Remove any of the following ASP.NET NuGet packages that are installed.</span></span> <span data-ttu-id="ff704-191">您將會移除這些使用封裝管理員主控台 (PMC)。</span><span class="sxs-lookup"><span data-stu-id="ff704-191">You will remove these using the Package Manager Console (PMC).</span></span> <span data-ttu-id="ff704-192">若要開啟 PMC，請選取**工具**功能表，然後選取**程式庫封裝管理員，**然後選取**Package Manager Console**。</span><span class="sxs-lookup"><span data-stu-id="ff704-192">To open the PMC, select the **Tools** menu and then select **Library Package Manager,** then select **Package Manager Console**.</span></span> <span data-ttu-id="ff704-193">您的專案可能不包括所有的這些。</span><span class="sxs-lookup"><span data-stu-id="ff704-193">Your project might not include all of these.</span></span>

    1. `Microsoft.AspNet.WebPages.Administration`  
 <span data-ttu-id="ff704-194">從 MVC 3 升級至 MVC 4 時，通常會將加入此封裝。</span><span class="sxs-lookup"><span data-stu-id="ff704-194">This package is typically added when upgrading from MVC 3 to MVC 4.</span></span> <span data-ttu-id="ff704-195">若要移除它，請在 PMC 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ff704-195">To remove it, run the following command in the PMC:</span></span>  
        `Uninstall-Package -Id Microsoft.AspNet.WebPages.Administration`
    2. `Microsoft-Web-Helpers`   
 <span data-ttu-id="ff704-196">此套件有品牌已重新命名為`Microsoft.AspNet.WebHelpers`。</span><span class="sxs-lookup"><span data-stu-id="ff704-196">This package has been rebranded as `Microsoft.AspNet.WebHelpers`.</span></span> <span data-ttu-id="ff704-197">若要移除它，請在 PMC 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ff704-197">To remove it, run the following command in the PMC:</span></span>  
        `Uninstall-Package -Id Microsoft-Web-Helpers`
    3. `Microsoft.AspNet.Mvc.FixedDisplayMode`  
 <span data-ttu-id="ff704-198">此套件包含因應措施的 MVC 5 中已修正問題的 MVC 4 中的 bug。</span><span class="sxs-lookup"><span data-stu-id="ff704-198">This package contains a work around for a bug in MVC 4 that has been fixed in MVC 5.</span></span> <span data-ttu-id="ff704-199">若要移除它，請在 PMC 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ff704-199">To remove it, run the following command in the PMC:</span></span>  
        `Uninstall-Package -Id Microsoft.AspNet.Mvc.FixedDisplayModes`
6. <span data-ttu-id="ff704-200">升級使用 pmc 依存的所有 ASP.NET NuGet 封裝。</span><span class="sxs-lookup"><span data-stu-id="ff704-200">Upgrade all the ASP.NET NuGet packages using the PMC.</span></span> <span data-ttu-id="ff704-201">在 PMC，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ff704-201">In the PMC, run the following command:</span></span>  
    `Update-Package`  
 <span data-ttu-id="ff704-202">`Update-Package`命令沒有任何參數將會更新每個套件。</span><span class="sxs-lookup"><span data-stu-id="ff704-202">The `Update-Package` command without any parameters will update every package.</span></span> <span data-ttu-id="ff704-203">您可以使用識別碼引數，個別更新封裝。</span><span class="sxs-lookup"><span data-stu-id="ff704-203">You can update packages individually by using the ID argument.</span></span> <span data-ttu-id="ff704-204">如需有關更新命令的詳細資訊，請執行`get-help update-package`。</span><span class="sxs-lookup"><span data-stu-id="ff704-204">For more information about the update command, run     `get-help update-package` .</span></span>

## <a name="update-the-application-webconfig-file"></a><span data-ttu-id="ff704-205">更新應用程式*web.config*檔案</span><span class="sxs-lookup"><span data-stu-id="ff704-205">Update the Application *web.config* File</span></span>

<span data-ttu-id="ff704-206">請務必在應用程式中進行這些變更*web.config*檔案無法*web.config*檔案*檢視*資料夾。</span><span class="sxs-lookup"><span data-stu-id="ff704-206">Be sure to make these changes in the app *web.config* file, not the *web.config* file in the *Views* folder.</span></span>

<span data-ttu-id="ff704-207">找出`<runtime>/<assemblyBinding>`區段，然後進行下列變更：</span><span class="sxs-lookup"><span data-stu-id="ff704-207">Locate the `<runtime>/<assemblyBinding>` section, and make the following changes:</span></span>

1. <span data-ttu-id="ff704-208">在名稱屬性為"system.web.mvc 的參考 」 的項目，變更從 「 4.0.0.0"到"5.0.0.0 」 版本數字。</span><span class="sxs-lookup"><span data-stu-id="ff704-208">In the elements with the name attribute "System.Web.Mvc", change the version number from "4.0.0.0" to "5.0.0.0".</span></span> <span data-ttu-id="ff704-209">（該元素中的兩個變更。）</span><span class="sxs-lookup"><span data-stu-id="ff704-209">(Two changes in that element.)</span></span>
2. <span data-ttu-id="ff704-210">在具有 name 屬性的項目&quot;System.Web.Helpers"和&quot;System.Web.WebPages&quot;變更從 「 2.0.0.0"的版本號碼，以 「 3.0.0.0"。</span><span class="sxs-lookup"><span data-stu-id="ff704-210">In elements with the name attribute &quot;System.Web.Helpers" and &quot;System.Web.WebPages&quot; change the version number from "2.0.0.0" to "3.0.0.0".</span></span> <span data-ttu-id="ff704-211">四項變更不會進行兩個在每個項目。</span><span class="sxs-lookup"><span data-stu-id="ff704-211">Four changes will occur, two in each of the elements.</span></span>

    [!code-xml[Main](how-to-upgrade-an-aspnet-mvc-4-and-web-api-project-to-aspnet-mvc-5-and-web-api-2/samples/sample3.xml?highlight=6,10,14)]
3. <span data-ttu-id="ff704-212">找出`<appSettings>`區段，並更新從 2.0.0.0.0 webpages:version 至 3.0.0.0，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ff704-212">Locate the `<appSettings>` section and update the webpages:version from 2.0.0.0.0 to 3.0.0.0 as shown below:</span></span>

    [!code-xml[Main](how-to-upgrade-an-aspnet-mvc-4-and-web-api-project-to-aspnet-mvc-5-and-web-api-2/samples/sample4.xml?highlight=2)]
4. <span data-ttu-id="ff704-213">移除任何不完整的信任層級。</span><span class="sxs-lookup"><span data-stu-id="ff704-213">Remove any trust levels other than Full.</span></span> <span data-ttu-id="ff704-214">例如: </span><span class="sxs-lookup"><span data-stu-id="ff704-214">For example:</span></span>

    [!code-xml[Main](how-to-upgrade-an-aspnet-mvc-4-and-web-api-project-to-aspnet-mvc-5-and-web-api-2/samples/sample5.xml?highlight=2)]

## <a name="update-the-webconfig-files-under-the-views-folder"></a><span data-ttu-id="ff704-215">更新*web.config* [檢視] 資料夾下的檔案</span><span class="sxs-lookup"><span data-stu-id="ff704-215">Update the *web.config* files under the Views folder</span></span>

<span data-ttu-id="ff704-216">如果您的應用程式使用的區域，您也必須更新每個*web.config*檔案*檢視*子資料夾的每個區域的資料夾。</span><span class="sxs-lookup"><span data-stu-id="ff704-216">If your application is using areas, you will also need to update each *web.config* file in the *Views* sub-folder of each Area folder.</span></span>

1. <span data-ttu-id="ff704-217">更新包含版本 」 4.0.0.0"版本"5.0.0.0"到"system.web.mvc 的參考 」 的所有項目。</span><span class="sxs-lookup"><span data-stu-id="ff704-217">Update all elements that contain "System.Web.Mvc" from version "4.0.0.0" to version "5.0.0.0".</span></span>  

    [!code-xml[Main](how-to-upgrade-an-aspnet-mvc-4-and-web-api-project-to-aspnet-mvc-5-and-web-api-2/samples/sample6.xml?highlight=2)]

    [!code-xml[Main](how-to-upgrade-an-aspnet-mvc-4-and-web-api-project-to-aspnet-mvc-5-and-web-api-2/samples/sample7.xml?highlight=4-6,8)]
2. <span data-ttu-id="ff704-218">更新包含 「 2.0.0.0"版版本 3.0.0.0 「 開始 」 到 「 System.Web.WebPages.Razor 」 的所有項目。</span><span class="sxs-lookup"><span data-stu-id="ff704-218">Update all elements that contain "System.Web.WebPages.Razor" from version "2.0.0.0" to version"3.0.0.0".</span></span> <span data-ttu-id="ff704-219">如果這個區段包含 「 System.Web.WebPages"，更新 「 3.0.0.0"版本從版本"2.0.0.0"這些項目</span><span class="sxs-lookup"><span data-stu-id="ff704-219">If this section contains "System.Web.WebPages", update those elements from version "2.0.0.0" to version"3.0.0.0"</span></span>  

    [!code-xml[Main](how-to-upgrade-an-aspnet-mvc-4-and-web-api-project-to-aspnet-mvc-5-and-web-api-2/samples/sample8.xml?highlight=3-5)]
3. <span data-ttu-id="ff704-220">如果您移除`Microsoft-Web-Helpers`NuGet 封裝在先前步驟中，安裝`Microsoft.AspNet.WebHelpers`使用 pmc 依存在下列命令：</span><span class="sxs-lookup"><span data-stu-id="ff704-220">If you removed the `Microsoft-Web-Helpers` NuGet package in a previous step, install `Microsoft.AspNet.WebHelpers` with the following command in the PMC:</span></span>  
    `Install-Package -Id Microsoft.AspNet.WebHelpers`
4. <span data-ttu-id="ff704-221">如果您的應用程式使用[User.IsInRole()](https://msdn.microsoft.com/en-us/library/system.web.security.roleprincipal.isinrole(v=vs.110).aspx)方法，將下列內容加入*Web.config*檔案。</span><span class="sxs-lookup"><span data-stu-id="ff704-221">If your app uses the [User.IsInRole()](https://msdn.microsoft.com/en-us/library/system.web.security.roleprincipal.isinrole(v=vs.110).aspx) method, add the following to the *Web.config* file.</span></span>

    [!code-xml[Main](how-to-upgrade-an-aspnet-mvc-4-and-web-api-project-to-aspnet-mvc-5-and-web-api-2/samples/sample9.xml)]

## <a name="final-steps"></a><span data-ttu-id="ff704-222">最後一個步驟</span><span class="sxs-lookup"><span data-stu-id="ff704-222">Final Steps</span></span>

<span data-ttu-id="ff704-223">建置及測試應用程式。</span><span class="sxs-lookup"><span data-stu-id="ff704-223">Build and test the application.</span></span>

<span data-ttu-id="ff704-224">從專案檔中移除 MVC 4 專案類型的 GUID。</span><span class="sxs-lookup"><span data-stu-id="ff704-224">Remove the MVC 4 project type GUID from the project files.</span></span>

1. <span data-ttu-id="ff704-225">在方案總管 中，以滑鼠右鍵按一下專案名稱，然後選取**卸載專案**。</span><span class="sxs-lookup"><span data-stu-id="ff704-225">In Solution Explorer, right-click the project name and then select **Unload Project**.</span></span>
2. <span data-ttu-id="ff704-226">以滑鼠右鍵按一下專案，然後選取 [編輯 projectname.csproj]。</span><span class="sxs-lookup"><span data-stu-id="ff704-226">Right-click the project and select Edit ProjectName.csproj.</span></span>
3. <span data-ttu-id="ff704-227">找出`ProjectTypeGuids`項目，然後移除 MVC 4 專案 GUID， `{E3E379DF-F4C6-4180-9B81-6769533ABE47}`。</span><span class="sxs-lookup"><span data-stu-id="ff704-227">Locate the `ProjectTypeGuids` element and then remove the MVC 4 project GUID, `{E3E379DF-F4C6-4180-9B81-6769533ABE47}`.</span></span>
4. <span data-ttu-id="ff704-228">儲存並關閉開啟的專案檔案。</span><span class="sxs-lookup"><span data-stu-id="ff704-228">Save and close the open project file.</span></span>
5. <span data-ttu-id="ff704-229">以滑鼠右鍵按一下專案，然後選取**重新載入專案**。</span><span class="sxs-lookup"><span data-stu-id="ff704-229">Right-click the project and select **Reload Project**.</span></span>