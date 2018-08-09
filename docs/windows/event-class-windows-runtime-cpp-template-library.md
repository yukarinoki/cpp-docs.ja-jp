---
title: イベント クラス (Windows ランタイム C++ テンプレート ライブラリ) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event
dev_langs:
- C++
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c07d58f244bf2e7e6c9329196bae7b5bb323ce12
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644165"
---
# <a name="event-class-windows-runtime-c-template-library"></a>Event クラス (Windows ランタイム C++ テンプレート ライブラリ)
イベントを表します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
class Event : public HandleT<HandleTraits::EventTraits>;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[Event::Event コンストラクター (Windows ランタイム C++ テンプレート ライブラリ)](../windows/event-event-constructor-windows-runtime-cpp-template-library.md)|新しいインスタンスを初期化、**イベント**クラス。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[Event::operator= 演算子](../windows/event-operator-assign-operator.md)|指定した割り当て**イベント**現在への参照を**イベント**インスタンス。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `HandleT`  
  
 `Event`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)