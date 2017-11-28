---
title: CorNativeType-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorNativeType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorNativeType
helpviewer_keywords: CorNativeType enumeration [.NET Framework metadata]
ms.assetid: e47a72f1-9609-48ed-bb34-97170d7f6890
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1c17abfc501b0d44981d2ed6cf7d69d60d9948b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="cornativetype-enumeration"></a><span data-ttu-id="4f33b-102">CorNativeType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="4f33b-102">CorNativeType Enumeration</span></span>
<span data-ttu-id="4f33b-103">Enthält Werte, die systemeigene, nicht verwaltete Typen beschreiben.</span><span class="sxs-lookup"><span data-stu-id="4f33b-103">Contains values that describe native unmanaged types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f33b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f33b-104">Syntax</span></span>  
  
```  
typedef enum CorNativeType {  
  
    NATIVE_TYPE_END                  = 0x0,  
    NATIVE_TYPE_VOID                 = 0x1,  
    NATIVE_TYPE_BOOLEAN              = 0x2,  
    NATIVE_TYPE_I1                   = 0x3,  
    NATIVE_TYPE_U1                   = 0x4,  
    NATIVE_TYPE_I2                   = 0x5,  
    NATIVE_TYPE_U2                   = 0x6,  
    NATIVE_TYPE_I4                   = 0x7,  
    NATIVE_TYPE_U4                   = 0x8,  
    NATIVE_TYPE_I8                   = 0x9,  
    NATIVE_TYPE_U8                   = 0xa,  
    NATIVE_TYPE_R4                   = 0xb,  
    NATIVE_TYPE_R8                   = 0xc,  
    NATIVE_TYPE_SYSCHAR              = 0xd,  
    NATIVE_TYPE_VARIANT              = 0xe,  
    NATIVE_TYPE_CURRENCY             = 0xf,  
    NATIVE_TYPE_PTR                  = 0x10,  
  
    NATIVE_TYPE_DECIMAL              = 0x11,  
    NATIVE_TYPE_DATE                 = 0x12,  
    NATIVE_TYPE_BSTR                 = 0x13,  
    NATIVE_TYPE_LPSTR                = 0x14,  
    NATIVE_TYPE_LPWSTR               = 0x15,  
    NATIVE_TYPE_LPTSTR               = 0x16,  
    NATIVE_TYPE_FIXEDSYSSTRING       = 0x17,  
    NATIVE_TYPE_OBJECTREF            = 0x18,  
    NATIVE_TYPE_IUNKNOWN             = 0x19,  
    NATIVE_TYPE_IDISPATCH            = 0x1a,  
    NATIVE_TYPE_STRUCT               = 0x1b,  
    NATIVE_TYPE_INTF                 = 0x1c,  
    NATIVE_TYPE_SAFEARRAY            = 0x1d,  
    NATIVE_TYPE_FIXEDARRAY           = 0x1e,  
    NATIVE_TYPE_INT                  = 0x1f,  
    NATIVE_TYPE_UINT                 = 0x20,  
  
    NATIVE_TYPE_NESTEDSTRUCT         = 0x21,  
    NATIVE_TYPE_BYVALSTR             = 0x22,  
    NATIVE_TYPE_ANSIBSTR             = 0x23,  
    NATIVE_TYPE_TBSTR                = 0x24,  
    NATIVE_TYPE_VARIANTBOOL          = 0x25,  
    NATIVE_TYPE_FUNC                 = 0x26,  
  
    NATIVE_TYPE_ASANY                = 0x28,  
    NATIVE_TYPE_ARRAY                = 0x2a,  
    NATIVE_TYPE_LPSTRUCT             = 0x2b,  
    NATIVE_TYPE_CUSTOMMARSHALER      = 0x2c,  
    NATIVE_TYPE_IINSPECTABLE         = 0x2e,  
    NATIVE_TYPE_HSTRING              = 0x2f,  
  
    NATIVE_TYPE_ERROR                = 0x2d,   
  
    NATIVE_TYPE_MAX                  = 0x50  
  
} CorNativeType;  
```  
  
## <a name="members"></a><span data-ttu-id="4f33b-105">Member</span><span class="sxs-lookup"><span data-stu-id="4f33b-105">Members</span></span>  
  
|<span data-ttu-id="4f33b-106">Member</span><span class="sxs-lookup"><span data-stu-id="4f33b-106">Member</span></span>|<span data-ttu-id="4f33b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f33b-107">Description</span></span>|  
|------------|-----------------|  
|`NATIVE_TYPE_END`|<span data-ttu-id="4f33b-108">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f33b-108">Obsolete.</span></span>|  
|`NATIVE_TYPE_VOID`|<span data-ttu-id="4f33b-109">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f33b-109">Obsolete.</span></span>|  
|`NATIVE_TYPE_BOOLEAN`|<span data-ttu-id="4f33b-110">Ein boolescher Wert 4-Byte, "true" ungleich 0 (null) und "false steht" ist NULL.</span><span class="sxs-lookup"><span data-stu-id="4f33b-110">A 4-byte Boolean value, where TRUE is non-zero and FALSE is zero.</span></span>|  
|`NATIVE_TYPE_I1`|<span data-ttu-id="4f33b-111">Eine 8-Bit-Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="4f33b-111">A signed 8-bit integer value.</span></span>|  
|`NATIVE_TYPE_U1`|<span data-ttu-id="4f33b-112">Eine 8-Bit-Ganzzahlwert ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="4f33b-112">An unsigned 8-bit integer value.</span></span>|  
|`NATIVE_TYPE_I2`|<span data-ttu-id="4f33b-113">Eine 16-Bit-Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="4f33b-113">A signed 16-bit integer value.</span></span>|  
|`NATIVE_TYPE_U2`|<span data-ttu-id="4f33b-114">Eine 16-Bit-Ganzzahlwert ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="4f33b-114">An unsigned 16-bit integer value.</span></span>|  
|`NATIVE_TYPE_I4`|<span data-ttu-id="4f33b-115">Ein 32-Bit-Ganzzahlwert mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="4f33b-115">A signed 32-bit integer value.</span></span>|  
|`NATIVE_TYPE_U4`|<span data-ttu-id="4f33b-116">Ein 32-Bit-Ganzzahlwert ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="4f33b-116">An unsigned 32-bit integer value.</span></span>|  
|`NATIVE_TYPE_I8`|<span data-ttu-id="4f33b-117">Eine 64-Bit-Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="4f33b-117">A signed 64-bit integer value.</span></span>|  
|`NATIVE_TYPE_U8`|<span data-ttu-id="4f33b-118">Ein 64-Bit-Ganzzahlwert ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="4f33b-118">An unsigned 64-bit integer value.</span></span>|  
|`NATIVE_TYPE_R4`|<span data-ttu-id="4f33b-119">Ein 4-Byte-Gleitkommazahl numerischer Wert.</span><span class="sxs-lookup"><span data-stu-id="4f33b-119">A 4-byte floating-point numeric value.</span></span>|  
|`NATIVE_TYPE_R8`|<span data-ttu-id="4f33b-120">Eine 8-Byte-Gleitkommazahl numerischer Wert.</span><span class="sxs-lookup"><span data-stu-id="4f33b-120">An 8-byte floating-point numeric value.</span></span>|  
|`NATIVE_TYPE_SYSCHAR`|<span data-ttu-id="4f33b-121">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f33b-121">Obsolete.</span></span>|  
|`NATIVE_TYPE_VARIANT`|<span data-ttu-id="4f33b-122">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f33b-122">Obsolete.</span></span>|  
|`NATIVE_TYPE_CURRENCY`|<span data-ttu-id="4f33b-123">Eine numerische COM-Typs, die verwaltete entspricht <xref:System.Decimal> Typ.</span><span class="sxs-lookup"><span data-stu-id="4f33b-123">A numeric COM type that corresponds to the managed <xref:System.Decimal> type.</span></span>|  
|`NATIVE_TYPE_PTR`|<span data-ttu-id="4f33b-124">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f33b-124">Obsolete.</span></span>|  
|`NATIVE_TYPE_DECIMAL`|<span data-ttu-id="4f33b-125">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f33b-125">Obsolete.</span></span>|  
|`NATIVE_TYPE_DATE`|<span data-ttu-id="4f33b-126">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f33b-126">Obsolete.</span></span>|  
|`NATIVE_TYPE_BSTR`|<span data-ttu-id="4f33b-127">COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="4f33b-127">COM Interop.</span></span>|  
|`NATIVE_TYPE_LPSTR`|<span data-ttu-id="4f33b-128">Ein Zeichenfolgenwert LPSTR.</span><span class="sxs-lookup"><span data-stu-id="4f33b-128">An LPSTR string value.</span></span>|  
|`NATIVE_TYPE_LPWSTR`|<span data-ttu-id="4f33b-129">Ein LPWSTR-Zeichenfolgenwert.</span><span class="sxs-lookup"><span data-stu-id="4f33b-129">An LPWSTR string value.</span></span>|  
|`NATIVE_TYPE_LPTSTR`|<span data-ttu-id="4f33b-130">Ein Zeichenfolgenwert LPTSTR.</span><span class="sxs-lookup"><span data-stu-id="4f33b-130">An LPTSTR string value.</span></span>|  
|`NATIVE_TYPE_FIXEDSYSSTRING`|<span data-ttu-id="4f33b-131">Ein fester, systemdefinierte Zeichenfolgenwert.</span><span class="sxs-lookup"><span data-stu-id="4f33b-131">A fixed, system-defined string value.</span></span>|  
|`NATIVE_TYPE_OBJECTREF`|<span data-ttu-id="4f33b-132">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f33b-132">Obsolete.</span></span>|  
|`NATIVE_TYPE_IUNKNOWN`|<span data-ttu-id="4f33b-133">COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="4f33b-133">COM Interop.</span></span>|  
|`NATIVE_TYPE_IDISPATCH`|<span data-ttu-id="4f33b-134">COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="4f33b-134">COM Interop.</span></span>|  
|`NATIVE_TYPE_STRUCT`|<span data-ttu-id="4f33b-135">Der Wert einer systemeigenen Struktur.</span><span class="sxs-lookup"><span data-stu-id="4f33b-135">A native structure value.</span></span>|  
|`NATIVE_TYPE_INTF`|<span data-ttu-id="4f33b-136">COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="4f33b-136">COM Interop.</span></span>|  
|`NATIVE_TYPE_SAFEARRAY`|<span data-ttu-id="4f33b-137">COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="4f33b-137">COM Interop.</span></span>|  
|`NATIVE_TYPE_FIXEDARRAY`|<span data-ttu-id="4f33b-138">Ein Wert des Arrays mit fester Länge.</span><span class="sxs-lookup"><span data-stu-id="4f33b-138">A fixed-length array value.</span></span>|  
|`NATIVE_TYPE_INT`|<span data-ttu-id="4f33b-139">Eine systemeigene 16-Bit-Ganzzahlwert mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="4f33b-139">A native 16-bit signed integer value.</span></span>|  
|`NATIVE_TYPE_UINT`|<span data-ttu-id="4f33b-140">Eine systemeigene 16-Bit-Ganzzahlwert ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="4f33b-140">A native 16-bit unsigned integer value.</span></span>|  
|`NATIVE_TYPE_NESTEDSTRUCT`|<span data-ttu-id="4f33b-141">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="4f33b-141">Obsolete.</span></span><br /><br /> <span data-ttu-id="4f33b-142">Verwenden Sie NATIVE_TYPE_STRUCT.</span><span class="sxs-lookup"><span data-stu-id="4f33b-142">Use NATIVE_TYPE_STRUCT.</span></span>|  
|`NATIVE_TYPE_BYVALSTR`|<span data-ttu-id="4f33b-143">COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="4f33b-143">COM Interop.</span></span>|  
|`NATIVE_TYPE_ANSIBSTR`|<span data-ttu-id="4f33b-144">COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="4f33b-144">COM Interop.</span></span>|  
|`NATIVE_TYPE_TBSTR`|<span data-ttu-id="4f33b-145">COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="4f33b-145">COM Interop.</span></span><br /><br /> <span data-ttu-id="4f33b-146">Wählen Sie je nach Plattform BSTR oder ANSIBSTR aus.</span><span class="sxs-lookup"><span data-stu-id="4f33b-146">Select BSTR or ANSIBSTR depending on the platform.</span></span>|  
|`NATIVE_TYPE_VARIANTBOOL`|<span data-ttu-id="4f33b-147">Ein boolescher 2-Byte-Wert, wobei "true" ist-1 und "false" ist NULL.</span><span class="sxs-lookup"><span data-stu-id="4f33b-147">A 2-byte Boolean value, where TRUE is -1 and FALSE is zero.</span></span>|  
|`NATIVE_TYPE_FUNC`|<span data-ttu-id="4f33b-148">Ein Funktionszeiger.</span><span class="sxs-lookup"><span data-stu-id="4f33b-148">A function pointer.</span></span>|  
|`NATIVE_TYPE_ASANY`|<span data-ttu-id="4f33b-149">Ein Verweis auf einen beliebigen systemeigenen Typ.</span><span class="sxs-lookup"><span data-stu-id="4f33b-149">A reference to any native type.</span></span>|  
|`NATIVE_TYPE_ARRAY`|<span data-ttu-id="4f33b-150">Ein Verweis auf ein Array mit Elementen eines nicht angegebenen Typs.</span><span class="sxs-lookup"><span data-stu-id="4f33b-150">A reference to an array with members of an unspecified type.</span></span>|  
|`NATIVE_TYPE_LPSTRUCT`|<span data-ttu-id="4f33b-151">Eine ganze 32-Bit-Zeiger auf eine Struktur.</span><span class="sxs-lookup"><span data-stu-id="4f33b-151">A 32-bit integer pointer to a structure.</span></span>|  
|`NATIVE_TYPE_CUSTOMMARSHALER`|<span data-ttu-id="4f33b-152">Einem benutzerdefinierten Marshaller systemeigenen Typ.</span><span class="sxs-lookup"><span data-stu-id="4f33b-152">A custom marshaler native type.</span></span><br /><br /> <span data-ttu-id="4f33b-153">Darauf muss durch eine Zeichenfolge im folgenden Format: "systemeigener Typ Name/0Name Marshaller type Name/0Optionaler Cookie/0" oder "{systemeigenen Typ GUID} / 0Name Marshaller type Name/0Optionaler Cookie/0"</span><span class="sxs-lookup"><span data-stu-id="4f33b-153">This must be followed by a string of the following format: "Native type name/0Custom marshaler type name/0Optional cookie/0" or "{Native type GUID}/0Custom marshaler type name/0Optional cookie/0"</span></span>|  
|`NATIVE_TYPE_ERROR`|<span data-ttu-id="4f33b-154">COM-Interop.</span><span class="sxs-lookup"><span data-stu-id="4f33b-154">COM Interop.</span></span><br /><br /> <span data-ttu-id="4f33b-155">Mit der ELEMENT_TYPE_I4 wird dieser Typ VT_HRESULT zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="4f33b-155">With ELEMENT_TYPE_I4 this type maps to VT_HRESULT.</span></span>|  
|`NATIVE_TYPE_IINSPECTABLE`|<span data-ttu-id="4f33b-156">Ein systemeigenes `IInspectable` Typ.</span><span class="sxs-lookup"><span data-stu-id="4f33b-156">A native `IInspectable` type.</span></span>|  
|`NATIVE_TYPE_HSTRING`|<span data-ttu-id="4f33b-157">Ein systemeigenes `HString`.</span><span class="sxs-lookup"><span data-stu-id="4f33b-157">A native `HString`.</span></span>|  
|`NATIVE_TYPE_MAX`|<span data-ttu-id="4f33b-158">Ein ungültiger Wert.</span><span class="sxs-lookup"><span data-stu-id="4f33b-158">An invalid value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f33b-159">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f33b-159">Requirements</span></span>  
 <span data-ttu-id="4f33b-160">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f33b-160">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f33b-161">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="4f33b-161">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="4f33b-162">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f33b-162">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f33b-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f33b-163">See Also</span></span>  
 <xref:System.Runtime.InteropServices.UnmanagedType>  
 [<span data-ttu-id="4f33b-164">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="4f33b-164">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)