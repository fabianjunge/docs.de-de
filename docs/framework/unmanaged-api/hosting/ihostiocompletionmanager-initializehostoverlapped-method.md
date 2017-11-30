---
title: IHostIoCompletionManager::InitializeHostOverlapped-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.InitializeHostOverlapped
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 26e8f9d963e6924a8c6abd73c3e025543c7d5b83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="31d39-102">IHostIoCompletionManager::InitializeHostOverlapped-Methode</span><span class="sxs-lookup"><span data-stu-id="31d39-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>
<span data-ttu-id="31d39-103">Ermöglicht es dem Host eine Möglichkeit, benutzerdefinierte Daten zum Anfügen an eine Win32 initialisieren `OVERLAPPED` -Struktur, die für asynchrone e/a-Anforderungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="31d39-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31d39-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="31d39-104">Syntax</span></span>  
  
```  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="31d39-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="31d39-105">Parameters</span></span>  
 `pvOverlapped`  
 <span data-ttu-id="31d39-106">[in] Ein Zeiger auf die Win32 `OVERLAPPED` Struktur mit der e/a-Anforderung eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="31d39-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31d39-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="31d39-107">Return Value</span></span>  
  
|<span data-ttu-id="31d39-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="31d39-108">HRESULT</span></span>|<span data-ttu-id="31d39-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31d39-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="31d39-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="31d39-110">S_OK</span></span>|<span data-ttu-id="31d39-111">`InitializeHostOverlapped`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="31d39-111">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="31d39-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="31d39-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="31d39-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="31d39-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="31d39-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="31d39-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="31d39-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="31d39-115">The call timed out.</span></span>|  
|<span data-ttu-id="31d39-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="31d39-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="31d39-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="31d39-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="31d39-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="31d39-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="31d39-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="31d39-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="31d39-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="31d39-120">E_FAIL</span></span>|<span data-ttu-id="31d39-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="31d39-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="31d39-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="31d39-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="31d39-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="31d39-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="31d39-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="31d39-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="31d39-125">Es war nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Ressource zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="31d39-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31d39-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="31d39-126">Remarks</span></span>  
 <span data-ttu-id="31d39-127">Die Windows-Plattform-Funktionen verwenden die `OVERLAPPED` Struktur zum Speichern von Status für asynchrone e/a-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="31d39-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="31d39-128">Die CLR ruft die `InitializeHostOverlapped` Methode, um dem Host das Anfügen von benutzerdefinierten Daten zu ermöglichen eine `OVERLAPPED` Instanz.</span><span class="sxs-lookup"><span data-stu-id="31d39-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="31d39-129">Um auf den Anfang des benutzerdefinierten Datenblocks zu erhalten, müssen Hosts den Offset der Größe der Festlegen der `OVERLAPPED` Struktur (`sizeof(OVERLAPPED)`).</span><span class="sxs-lookup"><span data-stu-id="31d39-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="31d39-130">Ein Rückgabewert von E_OUTOFMEMORY gibt an, dass der Host zum Initialisieren der benutzerdefinierten Daten fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="31d39-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="31d39-131">In diesem Fall wird die CLR meldet einen Fehler, und schlägt der Aufruf fehl.</span><span class="sxs-lookup"><span data-stu-id="31d39-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31d39-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="31d39-132">Requirements</span></span>  
 <span data-ttu-id="31d39-133">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31d39-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31d39-134">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="31d39-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="31d39-135">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="31d39-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="31d39-136">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31d39-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31d39-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31d39-137">See Also</span></span>  
 [<span data-ttu-id="31d39-138">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31d39-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="31d39-139">GetHostOverlappedSize-Methode</span><span class="sxs-lookup"><span data-stu-id="31d39-139">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)  
 [<span data-ttu-id="31d39-140">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31d39-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)