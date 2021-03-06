---
title: ICorProfilerCallback9::D ynamicmethodunloaded-Methode
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 2391ad854b17ec117940a3d3568c40d6cf7f4725
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498972"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a>ICorProfilerCallback9::D ynamicmethodunloaded-Methode
[Wird in der .NET Framework 4.7.2 und höheren Versionen unterstützt]  
  
Benachrichtigt den Profiler, wenn eine dynamische Methode in eine Garbage Collection und anschließend entladen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a>Parameter  
[in] `functionId`  
Der Bezeichner der in-Memory-Funktion, die in den Garbage Collection-und entladen wurde.

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerCallback8. dynamicmethodjitcompilationstarted-Methode](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [ICorProfilerCallback8. dynamicmethodjitcompilationabgeschlossene-Methode](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [ICorProfilerCallback9-Schnittstelle](icorprofilercallback9-interface.md)
- [COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS](cor-prf-high-monitor-enumeration.md)
