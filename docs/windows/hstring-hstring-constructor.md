---
title: Hstring::hstring コンス トラクター |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::HString
dev_langs:
- C++
ms.assetid: 6da12785-ed01-4720-a004-667db60298f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a3188e137d3a39fb26ca4151f72073306038e46f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="hstringhstring-constructor"></a>HString::HString コンストラクター
HString クラスの新しいインスタンスを初期化します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HString(HSTRING hstr = nullptr) throw();  
HString(HString&& other) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hstr`  
 HSTRING ハンドルの場合です。  
  
 `other`  
 既存の HString オブジェクト。  
  
## <a name="remarks"></a>コメント  
 最初のコンス トラクターは、空である新しい HString オブジェクトを初期化します。  
  
 2 番目のコンス トラクターは、既存の値に新しい HString オブジェクトを初期化します`other`パラメーターを破棄し、および、`other`パラメーター。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HString クラス](../windows/hstring-class.md)