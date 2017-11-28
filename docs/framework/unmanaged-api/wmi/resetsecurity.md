---
title: ResetSecurity-Funktion (Referenz zur nicht verwalteten API)
description: "Die ResetSecurity-Funktion weist ein Identitätswechseltoken für den aktuellen Thread."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: ResetSecurity
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: ResetSecurity
helpviewer_keywords: ResetSecurity function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2790012a429c6a0551d8321a80570f3f8be2142b
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="resetsecurity-function"></a><span data-ttu-id="904b0-103">ResetSecurity-Funktion</span><span class="sxs-lookup"><span data-stu-id="904b0-103">ResetSecurity function</span></span>
<span data-ttu-id="904b0-104">Weist den angegebenen Identitätstoken für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="904b0-104">Assigns the supplied impersonation token to the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="904b0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="904b0-105">Syntax</span></span>  
  
```  
HRESULT ResetSecurity (
   [in] HANDLE token
); 
```  

## <a name="parameters"></a><span data-ttu-id="904b0-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="904b0-106">Parameters</span></span>

`token`  
<span data-ttu-id="904b0-107">[in] Das Identitätstoken des aktuellen Threads zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="904b0-107">[in] The impersonation token to associate with the current thread.</span></span> <span data-ttu-id="904b0-108">Ihr Wert kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="904b0-108">Its value can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="904b0-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="904b0-109">Return value</span></span>

<span data-ttu-id="904b0-110">Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="904b0-110">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="904b0-111">Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null).</span><span class="sxs-lookup"><span data-stu-id="904b0-111">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="904b0-112">Um erweiterte Fehlerinformationen abzurufen, rufen Sie die [GetErrorInfo](geterrorinfo.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="904b0-112">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="904b0-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="904b0-113">Requirements</span></span>  
 <span data-ttu-id="904b0-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="904b0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="904b0-115">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="904b0-115">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="904b0-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="904b0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="904b0-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="904b0-117">See also</span></span>  
[<span data-ttu-id="904b0-118">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="904b0-118">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)