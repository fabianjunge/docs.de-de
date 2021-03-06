---
title: ICorProfilerInfo2::GetBoxClassLayout-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b9d775d5c386abeb100604250008ebf1bf377e8b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550811"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a>ICorProfilerInfo2::GetBoxClassLayout-Methode
Ruft Informationen über die auf dem sich der angegebene Werttyp befindet, wenn sie mittels Boxing konvertiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
#### <a name="parameters"></a>Parameter  
 `classId`  
 [in] Die ID der Klasse, die den Werttyp beschreibt, der mittels Boxing konvertiert wird.  
  
 `pBufferOffset`  
 [out] Eine ganze Zahl, die der Offset relativ zu der geschachteltes Objekt-ID-Zeiger, der den Werttyp ist.  
  
## <a name="remarks"></a>Hinweise  
 Die `pBufferOffset` Wert ist der Speicherort des Werttyps innerhalb eines Felds. Nach dem `pBufferOffset` wird angewendet, in ein geschachteltes Objekt Klassenlayout des Werttyps verwendet werden kann, um den Wert des Objekts zu interpretieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
