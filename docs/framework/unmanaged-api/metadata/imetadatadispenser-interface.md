---
title: IMetaDataDispenser-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenser
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenser
helpviewer_keywords: IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 989840b3-9822-4ce5-a6c5-b375d3340a7a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c5a0464f2fb7b81d98fcbb4b04bc465cf57b1b0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenser-interface"></a><span data-ttu-id="ec0ee-102">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ec0ee-102">IMetaDataDispenser Interface</span></span>
<span data-ttu-id="ec0ee-103">Stellt Methoden zum Erstellen eines neuen Bereichs für die Metadaten oder ein vorhandenes öffnen.</span><span class="sxs-lookup"><span data-stu-id="ec0ee-103">Provides methods to create a new metadata scope, or open an existing one.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ec0ee-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ec0ee-104">Methods</span></span>  
  
|<span data-ttu-id="ec0ee-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ec0ee-105">Method</span></span>|<span data-ttu-id="ec0ee-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec0ee-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ec0ee-107">DefineScope-Methode</span><span class="sxs-lookup"><span data-stu-id="ec0ee-107">DefineScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|<span data-ttu-id="ec0ee-108">Erstellt einen neuen Bereich im Arbeitsspeicher, in dem Sie neue Metadaten erstellen können.</span><span class="sxs-lookup"><span data-stu-id="ec0ee-108">Creates a new area in memory where you can create new metadata.</span></span>|  
|[<span data-ttu-id="ec0ee-109">OpenScope-Methode</span><span class="sxs-lookup"><span data-stu-id="ec0ee-109">OpenScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|<span data-ttu-id="ec0ee-110">Öffnet eine Datei vorhandene, auf dem Datenträger, und seine Metadaten in den Arbeitsspeicher zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ec0ee-110">Opens an existing, on-disk file and maps its metadata into memory.</span></span>|  
|[<span data-ttu-id="ec0ee-111">OpenScopeOnMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="ec0ee-111">OpenScopeOnMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|<span data-ttu-id="ec0ee-112">Öffnet einen Bereich des Arbeitsspeichers, die vorhandenen Metadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="ec0ee-112">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="ec0ee-113">Diese Methode öffnet, also einen angegebenen Bereich des Arbeitsspeichers, in denen die vorhandenen Daten als Metadaten behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="ec0ee-113">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ec0ee-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ec0ee-114">Requirements</span></span>  
 <span data-ttu-id="ec0ee-115">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec0ee-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec0ee-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ec0ee-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ec0ee-117">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="ec0ee-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ec0ee-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec0ee-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec0ee-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec0ee-119">See Also</span></span>  
 [<span data-ttu-id="ec0ee-120">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ec0ee-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="ec0ee-121">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ec0ee-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)