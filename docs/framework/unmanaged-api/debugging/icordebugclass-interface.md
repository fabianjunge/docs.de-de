---
title: ICorDebugClass-Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d12d952fe540b2ec36d058ae2100f0cf5c8e6bcf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710214"
---
# <a name="icordebugclass-interface1"></a>ICorDebugClass-Schnittstelle1
Stellt einen Typ dar, der entweder grundlegend oder komplex (das heißt benutzerdefiniert) sein kann. Wenn der Typ generisch ist, stellt `ICorDebugClass` den nicht instanziierten generischen Typ dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetModule-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|Ruft das Modul, das diese Klasse definiert.|  
|[GetStaticFieldValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|Ruft den Wert des angegebenen statischen Felds ab.|  
|[GetToken-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|Ruft die `TypeDef` Metadatentoken für diese Klasse.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugClass` Schnittstelle stellt einen nicht instanziierten generischen Typ dar. ICorDebugType-Schnittstelle stellt einen instanziierten generischen Typ dar. Z. B. `Hashtable<K, V>` durch dargestellt werden würde `ICorDebugClass`hingegen `Hashtable<Int32, String>` durch dargestellt werden würde `ICorDebugType`.  
  
 Nicht generische Typen werden von beiden dargestellt `ICorDebugClass` und `ICorDebugType`. Die zweite Schnittstelle wurde in .NET Framework, Version 2.0 für den Umgang mit Typinstanziierung eingeführt.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
