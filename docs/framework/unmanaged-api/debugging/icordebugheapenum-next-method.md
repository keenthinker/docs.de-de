---
title: ICorDebugHeapEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum::Next
helpviewer_keywords:
- ICorDebugHeapEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 2221fd06-9e27-4113-972e-2530db8c3594
topic_type:
- apiref
ms.openlocfilehash: 5d0b231b4014e60a9e8778c6b9d6ed7758b2d8c5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208472"
---
# <a name="icordebugheapenumnext-method"></a>ICorDebugHeapEnum::Next-Methode
Ruft die angegebene Anzahl von [COR_HEAPOBJECT](cor-heapobject-structure.md) Instanzen ab, die Informationen zu Objekten im verwalteten Heap enthalten.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parameter  
 celt  
 [in] Die Anzahl der abzurufenden Objekte.  
  
 Objekte  
 vorgenommen Ein Array von Zeigern, von denen jedes auf ein [COR_HEAPOBJECT](cor-heapobject-structure.md) Objekt verweist, das Informationen zu einem Objekt auf dem verwalteten Heap bereitstellt.  
  
 pceltFetched  
 vorgenommen Ein Zeiger auf die Anzahl der [COR_HEAPOBJECT](cor-heapobject-structure.md) -Objekte, die tatsächlich in zurückgegeben werden `objects` . Dieser Wert kann `null` sein, wenn `celt` 1 ist.  
  
## <a name="remarks"></a>Hinweise  
 Das `COR_HEAPOBJECT.type`-Feld ist der Bezeichner einer geschachtelten COM-Schnittstelle mit Referenzzählung. Diese Referenz muss von dem Aufrufer von `ICorDebugHeapEnum::Next` freigegeben werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugHeapEnum-Schnittstelle](icordebugheapenum-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
