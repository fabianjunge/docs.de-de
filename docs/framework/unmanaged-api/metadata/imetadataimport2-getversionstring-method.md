---
title: IMetaDataImport2::GetVersionString-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetVersionString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d08f43a790305c960d557064539de680a2d04af9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="bd5d0-102">IMetaDataImport2::GetVersionString-Methode</span><span class="sxs-lookup"><span data-stu-id="bd5d0-102">IMetaDataImport2::GetVersionString Method</span></span>
<span data-ttu-id="bd5d0-103">Ruft die Version der Laufzeit, die verwendet wurde, zum Erstellen der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="bd5d0-103">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd5d0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd5d0-104">Syntax</span></span>  
  
```  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd5d0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bd5d0-105">Parameters</span></span>  
 `pwzBuf`  
 <span data-ttu-id="bd5d0-106">[out] Ein Array zum Speichern der Zeichenfolge, die die Version angibt.</span><span class="sxs-lookup"><span data-stu-id="bd5d0-106">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="bd5d0-107">[in] Die Größe in Breitzeichen, der die `pwzBuf` Array.</span><span class="sxs-lookup"><span data-stu-id="bd5d0-107">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="bd5d0-108">[out] Die Anzahl der Breitzeichen, einschließlich eines null-Terminators zurückgegeben, der `pwzBuf` Array.</span><span class="sxs-lookup"><span data-stu-id="bd5d0-108">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd5d0-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bd5d0-109">Remarks</span></span>  
 <span data-ttu-id="bd5d0-110">Die `GetVersionString` Methode ruft die für die Version des aktuellen Metadatenbereich ab.</span><span class="sxs-lookup"><span data-stu-id="bd5d0-110">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="bd5d0-111">Wenn der Bereich nie gespeichert wurde, sind eine für die Version und eine leere Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bd5d0-111">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd5d0-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bd5d0-112">Requirements</span></span>  
 <span data-ttu-id="bd5d0-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd5d0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd5d0-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bd5d0-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd5d0-115">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="bd5d0-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bd5d0-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd5d0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd5d0-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd5d0-117">See Also</span></span>  
 [<span data-ttu-id="bd5d0-118">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd5d0-118">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="bd5d0-119">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd5d0-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)