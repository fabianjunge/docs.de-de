---
title: StrongNameErrorInfo-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameErrorInfo
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: StrongNameErrorInfo
helpviewer_keywords: StrongNameErrorInfo function [.NET Framework strong naming]
ms.assetid: e91bf8c3-7c26-4732-938e-2e5b04abfc99
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0fbe77f16ed022458a036b6627b82f80d194276c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="strongnameerrorinfo-function"></a><span data-ttu-id="f83a8-102">StrongNameErrorInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="f83a8-102">StrongNameErrorInfo Function</span></span>
<span data-ttu-id="f83a8-103">Ruft den letzten Fehlercode ab, der von einer der Funktionen mit starkem Namen ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="f83a8-103">Gets the last error code that was raised by one of the strong name functions.</span></span>  
  
 <span data-ttu-id="f83a8-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="f83a8-104">This function has been deprecated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f83a8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f83a8-105">Syntax</span></span>  
  
```  
HRESULT StrongNameErrorInfo ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="f83a8-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f83a8-106">Return Value</span></span>  
 <span data-ttu-id="f83a8-107">Der letzte com-Fehlercode festlegen, indem eine der Funktionen mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="f83a8-107">The last COM error code set by one of the strong name functions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f83a8-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f83a8-108">Remarks</span></span>  
 <span data-ttu-id="f83a8-109">Die meisten Methoden mit starkem Namen zurückgeben ein einfachen `true` oder `false` Angabe der erfolgreichen Beendigung.</span><span class="sxs-lookup"><span data-stu-id="f83a8-109">Most of the strong name methods return a simple `true` or `false` indication of successful completion.</span></span> <span data-ttu-id="f83a8-110">Verwenden der `StrongNameErrorInfo` Funktion, um einen HRESULT-Wert abzurufen, der angibt, den letzten Fehler, die von Funktionen mit starkem Namen generiert.</span><span class="sxs-lookup"><span data-stu-id="f83a8-110">Use the `StrongNameErrorInfo` function to retrieve an HRESULT that specifies the last error generated by the strong name functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f83a8-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f83a8-111">Requirements</span></span>  
 <span data-ttu-id="f83a8-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f83a8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f83a8-113">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="f83a8-113">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f83a8-114">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f83a8-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f83a8-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f83a8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f83a8-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f83a8-116">See Also</span></span>  
 [<span data-ttu-id="f83a8-117">Starke Namen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="f83a8-117">Strong Naming Global Static Functions</span></span>](http://msdn.microsoft.com/en-us/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)