---
title: ISymUnmanagedWriter::DefineGlobalVariable-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineGlobalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable method [.NET Framework debugging]
- DefineGlobalVariable method [.NET Framework debugging]
ms.assetid: 843c904a-8176-4d8f-bd47-b4d4c29f4c5c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 920c768523e422220862b04fa069fc8cbea8960a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54677705"
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a>ISymUnmanagedWriter::DefineGlobalVariable-Methode
Definiert eine einzelne globale Variable.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DefineGlobalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a>Parameter  
 `name`  
 [in] Ein Zeiger auf eine `WCHAR` , der Name den globalen Variablen definiert.  
  
 `attributes`  
 [in] Der globalen Variablenattribute.  
  
 `cSig`  
 [in] Ein `ULONG32` , die Größe in Zeichen angibt, der die `signature` Puffer.  
  
 `signature`  
 [in] Die Signatur der globalen Variablen.  
  
 `addrKind`  
 [in] Der Adresstyp.  
  
 `addr1`  
 [in] Die erste Adresse für die Parameterangabe.  
  
 `addr2`  
 [in] Die zweite Adresse für die Parameterangabe.  
  
 `addr3`  
 [in] Die dritte Adresse für die Parameterangabe.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch
- [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [DefineLocalVariable-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
- [DefineGlobalVariable2-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)
