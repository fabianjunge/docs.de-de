---
title: ICorProfilerInfo2::GetGenerationBounds-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetGenerationBounds
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetGenerationBounds
helpviewer_keywords:
- ICorProfilerInfo2::GetGenerationBounds method [.NET Framework profiling]
- GetGenerationBounds method [.NET Framework profiling]
ms.assetid: 9c37185f-d1e0-4a6e-8b99-707f7df61d88
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 33f1e130d214e28b8153b1aaf722c3df97edef37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getgenerationbounds-method"></a><span data-ttu-id="5e0e7-102">ICorProfilerInfo2::GetGenerationBounds-Methode</span><span class="sxs-lookup"><span data-stu-id="5e0e7-102">ICorProfilerInfo2::GetGenerationBounds Method</span></span>
<span data-ttu-id="5e0e7-103">Ruft die Arbeitsspeicherbereiche ab, die Segmente des Heaps sind, aus dem sich die verschiedenen Garbage Collection-Generationen zusammensetzen.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-103">Gets the memory regions, which are segments of the heap, that make up the various garbage collection generations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e0e7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e0e7-104">Syntax</span></span>  
  
```  
HRESULT GetGenerationBounds(  
    [in]  ULONG cObjectRanges,  
    [out] ULONG *pcObjectRanges,  
    [out, size_is(cObjectRanges), length_is(*pcObjectRanges)] COR_PRF_GC_GENERATION_RANGE ranges[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5e0e7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5e0e7-105">Parameters</span></span>  
 `cObjectRanges`  
 <span data-ttu-id="5e0e7-106">[in] Die Anzahl der Elemente, die der Aufrufer dem `ranges`-Array zugeordnet hat.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-106">[in] The number of elements allocated by the caller for the `ranges` array.</span></span>  
  
 `pcObjectRanges`  
 <span data-ttu-id="5e0e7-107">[out] Ein Zeiger auf eine ganze Zahl, die die Gesamtzahl der Bereiche angibt, von denen einige oder alle im `ranges`-Array zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-107">[out] A pointer to an integer that specifies the total number of ranges, some or all of which will be returned in the `ranges` array.</span></span>  
  
 `ranges`  
 <span data-ttu-id="5e0e7-108">[out] Ein Array von [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) Strukturen, von denen jedes einen Bereich (d. h. einen Block) des Arbeitsspeichers innerhalb der Generation, die Garbagecollection unterzogen wird beschreibt.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-108">[out] An array of [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structures, each of which describes a range (that is, block) of memory within the generation that is undergoing garbage collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e0e7-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5e0e7-109">Remarks</span></span>  
 <span data-ttu-id="5e0e7-110">Die `GetGenerationBounds`-Methode kann von jedem Profilerrückruf aufgerufen werden, solange die Garbage Collection nicht durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-110">The `GetGenerationBounds` method can be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="5e0e7-111">Es kann also aufgerufen werden, von einem beliebigen Rückruf mit Ausnahme von those, die occur an zwischen [ICorProfilerCallback2:: GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) und [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="5e0e7-111">That is, it can be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
 <span data-ttu-id="5e0e7-112">Die meisten Generationenverschiebungen finden während der Garbage Collections statt.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-112">Most shifting of generations takes place during garbage collections.</span></span> <span data-ttu-id="5e0e7-113">Generationen können zwischen Auflistungen anwachsen, verschieben sich im Allgemeinen jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-113">Generations might grow between collections but generally do not move around.</span></span> <span data-ttu-id="5e0e7-114">Deshalb befinden sich die interessantesten Positionen zum Aufrufen von `GetGenerationBounds` in `ICorProfilerCallback2::GarbageCollectionStarted` und `ICorProfilerCallback2::GarbageCollectionFinished`.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-114">Therefore, the most interesting places to call `GetGenerationBounds` are in `ICorProfilerCallback2::GarbageCollectionStarted` and `ICorProfilerCallback2::GarbageCollectionFinished`.</span></span>  
  
 <span data-ttu-id="5e0e7-115">Während des Programmstarts werden einige Objekte in der Regel in den Generationen 3 und 0 von der Common Language Runtime (CLR) selbst zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-115">During program startup, some objects are allocated by the common language runtime (CLR) itself, generally in generations 3 and 0.</span></span> <span data-ttu-id="5e0e7-116">Daher enthalten diese Generationen zu dem Zeitpunkt, an dem der verwaltete Code die Ausführung startet, bereits Objekte.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-116">Thus, by the time managed code starts executing, these generations will already contain objects.</span></span> <span data-ttu-id="5e0e7-117">Die Generationen 1 und 2 sind normalerweise (bis auf vom Garbage Collector generierte Dummyobjekte) leer.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-117">Generations 1 and 2 will normally be empty, except for dummy objects that are generated by the garbage collector.</span></span> <span data-ttu-id="5e0e7-118">(Die Größe der Dummyobjekte beträgt in 32-Bit-Implementierungen der CLR 12 Bytes. In 64-Bit-Implementierungen sind diese Objekte größer.) Es sind möglicherweise auch Bereiche der Generation 2 in den Modulen vorhanden, die von Native Image Generator ("NGen.exe") erzeugt wurden.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-118">(The size of dummy objects is 12 bytes in 32-bit implementations of the CLR; the size is larger in 64-bit implementations.) You might also see generation 2 ranges that are inside modules produced by the Native Image Generator (NGen.exe).</span></span> <span data-ttu-id="5e0e7-119">In diesem Fall werden von die Objekten in Generation 2 *fixierte Objekte*, die beim Ausführen von NGen.exe und nicht vom Garbage Collector reserviert werden.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-119">In this case, the objects in generation 2 are *frozen objects*, which are allocated when NGen.exe runs rather than by the garbage collector.</span></span>  
  
 <span data-ttu-id="5e0e7-120">Diese Funktion verwendet vom Aufrufer reservierte Puffer.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-120">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e0e7-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5e0e7-121">Requirements</span></span>  
 <span data-ttu-id="5e0e7-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e0e7-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e0e7-123">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5e0e7-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5e0e7-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e0e7-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e0e7-125">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e0e7-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e0e7-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e0e7-126">See Also</span></span>  
 [<span data-ttu-id="5e0e7-127">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e0e7-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="5e0e7-128">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e0e7-128">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [<span data-ttu-id="5e0e7-129">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5e0e7-129">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="5e0e7-130">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="5e0e7-130">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)