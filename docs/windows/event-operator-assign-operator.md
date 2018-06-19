---
title: Event::operator = 演算子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: d8fe9820-8856-4899-9553-56226bdc4945
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d3da41ff7fd145889ec799bb2f8ebe99aed36934
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33871124"
---
# <a name="eventoperator-operator"></a>Event::operator= 演算子
指定された Event 参照を現在の Event インスタンスに割り当てます。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW Event& operator=(  
   _Inout_ Event&& h  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `h`  
 イベント インスタンスに右辺値の参照。  
  
## <a name="return-value"></a>戻り値  
 現在の Event インスタンスへのポインター。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [Event クラス (Windows ランタイム C++ テンプレート ライブラリ)](../windows/event-class-windows-runtime-cpp-template-library.md)