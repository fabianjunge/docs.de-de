---
title: ICorDebugVariableHome::GetRegister-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetRegister
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f16e4bfe4767e1b49d7dacf0481e8911a90e178
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="843a4-102">ICorDebugVariableHome::GetRegister-Methode</span><span class="sxs-lookup"><span data-stu-id="843a4-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="843a4-103">Ruft die Registrierung, die eine Variable mit einem Speicherort enthält `VLT_REGISTER`, und die Basisregister für eine Variable mit einem Speicherort `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="843a4-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="843a4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="843a4-104">Syntax</span></span>  
  
```  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="843a4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="843a4-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="843a4-106">[out] Ein CorDebugRegister-Enumerationswert, der die Registrierung für eine Variable mit einem Speicherort angibt `VLT_REGISTER`, und die Basisregister für eine Variable mit einem Speicherort `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="843a4-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="843a4-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="843a4-107">Return Value</span></span>  
 <span data-ttu-id="843a4-108">Die Methode gibt die folgenden Werte zurück:</span><span class="sxs-lookup"><span data-stu-id="843a4-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="843a4-109">Wert</span><span class="sxs-lookup"><span data-stu-id="843a4-109">Value</span></span>|<span data-ttu-id="843a4-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="843a4-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="843a4-111">Die Variable ist, in dem Register, angegeben durch die `pRegister` Argument.</span><span class="sxs-lookup"><span data-stu-id="843a4-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="843a4-112">Die Variable ist nicht in ein Register oder an einem Speicherort relativ zum Registrieren.</span><span class="sxs-lookup"><span data-stu-id="843a4-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="843a4-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="843a4-113">Requirements</span></span>  
 <span data-ttu-id="843a4-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="843a4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="843a4-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="843a4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="843a4-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="843a4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="843a4-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="843a4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="843a4-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="843a4-118">See Also</span></span>  
 [<span data-ttu-id="843a4-119">VariableLocationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="843a4-119">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 [<span data-ttu-id="843a4-120">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="843a4-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)