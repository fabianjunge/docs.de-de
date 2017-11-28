---
title: IMethodMalloc::Alloc-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMethodMalloc.Alloc
api_location: mscorwks.dll
api_type: COM
f1_keywords: IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ae0fa84c08cb8e366db36b6727a3058f24789801
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="imethodmallocalloc-method"></a><span data-ttu-id="d7456-102">IMethodMalloc::Alloc-Methode</span><span class="sxs-lookup"><span data-stu-id="d7456-102">IMethodMalloc::Alloc Method</span></span>
<span data-ttu-id="d7456-103">Versucht, eine bestimmte Arbeitsspeichermenge für einen neuen Microsoft intermediate Language (MSIL)-Funktionsrumpf belegt werden.</span><span class="sxs-lookup"><span data-stu-id="d7456-103">Attempts to allocate a specified amount of memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7456-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7456-104">Syntax</span></span>  
  
```  
PVOID Alloc (  
    [in] ULONG   cb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d7456-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d7456-105">Parameters</span></span>  
 `cb`  
 <span data-ttu-id="d7456-106">[in] Die Anzahl der Bytes, die für den Methodentext zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d7456-106">[in] The number of bytes to allocate for the method body.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7456-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d7456-107">Remarks</span></span>  
 <span data-ttu-id="d7456-108">Der belegte Arbeitsspeicher beginnt an einer Adresse, die größer als die Basisadresse des Moduls, das diese Zuweisung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d7456-108">The allocated memory will begin at an address greater than the base address of the module that is associated with this allocator.</span></span> <span data-ttu-id="d7456-109">In anderen Worten, jede Zuweisung wird für ein bestimmtes Modul erstellt und versucht, mit einem positiven Offset von seiner Basisadresse belegt werden.</span><span class="sxs-lookup"><span data-stu-id="d7456-109">In other words, each allocator is created for a particular module, and will attempt to allocate memory at a positive offset from its base address.</span></span> <span data-ttu-id="d7456-110">Wenn `Alloc` nicht belegen kann die angeforderte Anzahl von Bytes an einer Adresse, die größer als die Basisadresse des Moduls, unabhängig von der tatsächlichen Menge des freien Speichers E_OUTOFMEMORY zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d7456-110">If `Alloc` fails to allocate the requested number of bytes at an address greater than the base address of the module, it returns E_OUTOFMEMORY, regardless of the actual amount of memory space available.</span></span>  
  
 <span data-ttu-id="d7456-111">Die `Alloc` -Methode sollte verwendet werden, zusammen mit den [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="d7456-111">The `Alloc` method should be used in conjunction with the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7456-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d7456-112">Requirements</span></span>  
 <span data-ttu-id="d7456-113">**Plattformen:** WindSee [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7456-113">**Platforms:** WindSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7456-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d7456-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d7456-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7456-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7456-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7456-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7456-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7456-117">See Also</span></span>  
 [<span data-ttu-id="d7456-118">IMethodMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d7456-118">IMethodMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)