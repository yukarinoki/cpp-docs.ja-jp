---
title: Hstringreference::hstringreference コンス トラクター |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference
dev_langs:
- C++
ms.assetid: 29f5fe11-3928-4f60-9861-f0894247bfcb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dc88ea32d4384b36559a4a10da0a5975345bf0d7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876008"
---
# <a name="hstringreferencehstringreference-constructor"></a>HStringReference::HStringReference コンストラクター
HStringReference クラスの新しいインスタンスを初期化します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template<unsigned int sizeDest>  
HStringReference(wchar_t const (&str)[ sizeDest]) throw();  
  
template<unsigned int sizeDest>  
HStringReference(wchar_t const (&str)[ sizeDest],   
                 unsigned int len) throw();  
  
HStringReference(HStringReference&& other) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `sizeDest`  
 コピー先の HStringReference バッファーのサイズを指定するテンプレート パラメーター。  
  
 `str`  
 ワイド文字の文字列への参照。  
  
 `len`  
 最大長、`str`この操作で使用するパラメーター バッファーです。 場合、`len`パラメーターが指定されていない全体`str`パラメーターを使用します。 場合`len`がより大きい`sizeDest`、`len`に設定されている`sizeDest`-1 です。  
  
 `other`  
 別の HStringReference オブジェクトです。  
  
## <a name="remarks"></a>コメント  
 最初のコンス トラクターがパラメーターとしてのサイズを同じ新規の HStringReference オブジェクトを初期化します`str`です。  
  
 2 番目のコンス トラクター初期化新しい HStringReference オブジェクトをパラメーターでサイズ specifeid`len`です。  
  
 3 番目コンス トラクターは、新しい HStringReference オブジェクトの値を`other`パラメーターを破棄し、および、`other`パラメーター。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HStringReference クラス](../windows/hstringreference-class.md)