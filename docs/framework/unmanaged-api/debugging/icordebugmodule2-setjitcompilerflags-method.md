---
title: ICorDebugModule2::SetJITCompilerFlags-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e605859a3049abc0c17d9d6792ade78f4ad2bd78
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417361"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a>ICorDebugModule2::SetJITCompilerFlags-Methode
Legt die Flags, die die Just-in-Time (JIT)-Kompilierung für diese ICorDebugModule2 steuern.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwFlags`  
 [in] Eine bitweise Kombination der [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) Enumerationswerte.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die `dwFlags` Wert ist ungültig, die `SetJITCompilerFlags` Methode fehl.  
  
 Die `SetJITCompilerFlags` Methode kann aufgerufen werden, nur von innerhalb der [ICorDebugManagedCallback:: LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) Rückruf für dieses Modul. Versucht, die sie nach dem Aufrufen der `ICorDebugManagedCallback::LoadModule` Rückruf übermittelt wurde, schlägt fehl.  
  
 Bearbeiten und Fortfahren wird auf 64-Bit- oder Win9x-Plattformen nicht unterstützt. Aus diesem Grund beim Aufrufen der `SetJITCompilerFlags` -Methode auf einer dieser beiden Plattformen mit dem CORDEBUG_JIT_ENABLE_ENC-Flag festgelegt `dwFlags`, die `SetJITCompilerFlags` -Methode und alle spezifischen Methoden zum Bearbeiten und fortfahren, z. B. [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), schlägt fehl.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
