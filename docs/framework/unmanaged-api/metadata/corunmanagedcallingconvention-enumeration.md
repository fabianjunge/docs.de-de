---
title: CorUnmanagedCallingConvention-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorUnmanagedCallingConvention
api_location: mscoree.dll
api_type: COM
f1_keywords: CorUnmanagedCallingConvention
helpviewer_keywords: CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f66cb036de8450d4c1b3431b92487260956d47f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="abefb-102">CorUnmanagedCallingConvention-Enumeration</span><span class="sxs-lookup"><span data-stu-id="abefb-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="abefb-103">Gibt die Aufrufkonventionen für nicht verwalteten Code an.</span><span class="sxs-lookup"><span data-stu-id="abefb-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abefb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="abefb-104">Syntax</span></span>  
  
```  
typedef enum CorUnmanagedCallingConvention {  
  
    IMAGE_CEE_UNMANAGED_CALLCONV_C         = 0x1,  
    IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL   = 0x2,  
    IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL  = 0x3,  
    IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL  = 0x4,  
  
    IMAGE_CEE_CS_CALLCONV_C                = 0x1,  
    IMAGE_CEE_CS_CALLCONV_STDCALL          = 0x2,  
    IMAGE_CEE_CS_CALLCONV_THISCALL         = 0x3,  
    IMAGE_CEE_CS_CALLCONV_FASTCALL         = 0x4  
  
} CorUnmanagedCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="abefb-105">Member</span><span class="sxs-lookup"><span data-stu-id="abefb-105">Members</span></span>  
  
|<span data-ttu-id="abefb-106">Member</span><span class="sxs-lookup"><span data-stu-id="abefb-106">Member</span></span>|<span data-ttu-id="abefb-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="abefb-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="abefb-108">C-Sprache-Aufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="abefb-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="abefb-109">Die herkömmliche Aufrufkonventionen.</span><span class="sxs-lookup"><span data-stu-id="abefb-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="abefb-110">Die "this" Aufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="abefb-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="abefb-111">Die "schnelle" Aufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="abefb-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="abefb-112">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="abefb-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="abefb-113">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="abefb-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="abefb-114">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="abefb-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="abefb-115">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="abefb-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abefb-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="abefb-116">Remarks</span></span>  
 <span data-ttu-id="abefb-117">Die CLR unterstützt nicht die "schnelle" Aufrufkonvention in .NET Framework, Version 1.0.</span><span class="sxs-lookup"><span data-stu-id="abefb-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abefb-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="abefb-118">Requirements</span></span>  
 <span data-ttu-id="abefb-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abefb-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abefb-120">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="abefb-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="abefb-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abefb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abefb-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="abefb-122">See Also</span></span>  
 [<span data-ttu-id="abefb-123">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="abefb-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)