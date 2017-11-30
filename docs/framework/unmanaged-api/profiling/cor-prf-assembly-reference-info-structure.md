---
title: COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 000a338400efa0d70e690f585518304a8b525346
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="corprfassemblyreferenceinfo-structure"></a><span data-ttu-id="b582f-102">COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="b582f-102">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>
<span data-ttu-id="b582f-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="b582f-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b582f-104">Liefert der Common Language Runtime Informationen über einen Assemblyverweis, der beachtet werden muss, wenn ein Assemblyverweis-Abschlussdurchlauf durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b582f-104">Provides the common language runtime with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b582f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b582f-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_ASSEMBLY_REFERENCE_INFO {  
    void* pbPublicKeyOrToken;  
    ULONG cbPublicKeyOrToken;  
    LPCWSTR szName;  
    ASSEMBLYMETADATA* pMetaData;  
    void* pbHashValue;  
    ULONG cbHashValue;  
    DWORD dwAssemblyRefFlags;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="b582f-106">Member</span><span class="sxs-lookup"><span data-stu-id="b582f-106">Members</span></span>  
  
|<span data-ttu-id="b582f-107">Member</span><span class="sxs-lookup"><span data-stu-id="b582f-107">Member</span></span>|<span data-ttu-id="b582f-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b582f-108">Description</span></span>|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|<span data-ttu-id="b582f-109">Ein Zeiger auf einen öffentlichen Schlüssel oder ein Token der Assembly.</span><span class="sxs-lookup"><span data-stu-id="b582f-109">A pointer to the public key or token of the assembly.</span></span>|  
|`cbPublicKeyOrToken`|<span data-ttu-id="b582f-110">Die Anzahl der Bytes im öffentlichen Schlüssel oder im Token.</span><span class="sxs-lookup"><span data-stu-id="b582f-110">The number of bytes in the public key or token.</span></span>|  
|`szName`|<span data-ttu-id="b582f-111">Der Name derAssembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b582f-111">The name of the assembly that is referenced.</span></span>|  
|`pMetaData`|<span data-ttu-id="b582f-112">Ein Zeiger auf die Metadaten der Assembly.</span><span class="sxs-lookup"><span data-stu-id="b582f-112">A pointer to the assembly's metadata.</span></span>|  
|`pbHashValue`|<span data-ttu-id="b582f-113">Ein Zeiger auf ein Hash-Binary Large Object (BLOB).</span><span class="sxs-lookup"><span data-stu-id="b582f-113">A pointer to a hash binary large object (BLOB).</span></span>|  
|`cbHashValue`|<span data-ttu-id="b582f-114">Die Anzahl von Bytes im Hash-BLOB.</span><span class="sxs-lookup"><span data-stu-id="b582f-114">The number of bytes in the hash BLOB.</span></span>|  
|`dwAssemblyRefFlags`|<span data-ttu-id="b582f-115">Die Flags der Assembly.</span><span class="sxs-lookup"><span data-stu-id="b582f-115">The assembly's flags.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b582f-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b582f-116">Remarks</span></span>  
 <span data-ttu-id="b582f-117">Die `COR_PRF_EX_CLAUSE_INFO`-Struktur wird vom Profiler gefüllt, wenn zusätzliche Assemblyverweise deklariert werden, die beachtet werden müssen, wenn ein Assemblyverweis-Abschlussdurchlauf durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b582f-117">The `COR_PRF_EX_CLAUSE_INFO` structure is populated by the profiler when it declares additional assembly references that the common language runtime should consider when performing an assembly reference closure walk.</span></span>  
  
 <span data-ttu-id="b582f-118">Wenn der Profiler für registriert die [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Rückrufmethode darstellt, die Common Language Runtime übergibt, der Pfad und Name der Assembly geladen und zusammen mit einem Zeiger auf eine [ ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) -Schnittstellenobjekt an diese Methode.</span><span class="sxs-lookup"><span data-stu-id="b582f-118">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="b582f-119">Der Profiler ruft dann die [AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) Methode mit einem `COR_PRF_ASSEMBLY_REFERENCE_INFO` -Objekt für jede Zielassembly auf aus der Assembly aus verweisen die [ Icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="b582f-119">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b582f-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b582f-120">Requirements</span></span>  
 <span data-ttu-id="b582f-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b582f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b582f-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b582f-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b582f-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b582f-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b582f-124">**.NET Framework-Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b582f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b582f-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b582f-125">See Also</span></span>  
 [<span data-ttu-id="b582f-126">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="b582f-126">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)  
 [<span data-ttu-id="b582f-127">GetAssemblyReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="b582f-127">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)  
 [<span data-ttu-id="b582f-128">AddAssemblyReference-Methode</span><span class="sxs-lookup"><span data-stu-id="b582f-128">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)