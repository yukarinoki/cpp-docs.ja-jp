---
title: Event::event コンス トラクター (Windows ランタイム C++ テンプレート ライブラリ) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event::Event
dev_langs:
- C++
ms.assetid: 21495297-9612-4095-9256-16e168cc0021
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: de0f68ee3e27f2ac3a7f87e64489a05a16dcdc91
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "39571413"
---
# <a name="eventevent-constructor-windows-runtime-c-template-library"></a>Event::Event コンストラクター (Windows ランタイム C++ テンプレート ライブラリ)
Event クラスの新しいインスタンスを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
explicit Event(  
   HANDLE h = HandleT::Traits::GetInvalidValue()  
);  
WRL_NOTHROW Event(  
   _Inout_ Event&& h  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *h*  
 イベントに対するハンドル。 既定では、 *h*に初期化されます**nullptr**します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [Event クラス (Windows ランタイム C++ テンプレート ライブラリ)](../windows/event-class-windows-runtime-cpp-template-library.md)