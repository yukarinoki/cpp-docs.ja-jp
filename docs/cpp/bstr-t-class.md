---
title: _bstr_t クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t
dev_langs:
- C++
helpviewer_keywords:
- BSTR object
- _bstr_t class
- BSTR object [C++], COM encapsulation
ms.assetid: 58841fef-fe21-4a84-aab9-780262b5201f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 15ed9c32a204bdef726a5ace88d811d2eeeb2c53
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027249"
---
# <a name="bstrt-class"></a>_bstr_t クラス
**Microsoft 固有の仕様**  
  
 A`_bstr_t`オブジェクトによってカプセル化、 [BSTR データ型](http://msdn.microsoft.com/1b2d7d2c-47af-4389-a6b6-b01b7e915228)します。 クラスは、管理リソースの割り当てと割り当て解除関数の呼び出しを通じて`SysAllocString`と`SysFreeString`およびその他の`BSTR`ときに適切な Api。 `_bstr_t` クラスは、参照カウントを使用して過剰なオーバーヘッドを回避します。  
  
### <a name="construction"></a>構築  
  
|||  
|-|-|  
|[_bstr_t](../cpp/bstr-t-bstr-t.md)|`_bstr_t` オブジェクトを構築します。|  
  
### <a name="operations"></a>オペレーション  
  
|||  
|-|-|  
|[割り当てる](../cpp/bstr-t-assign.md)|`BSTR` を `BSTR` でラップされた `_bstr_t` にコピーします。|  
|[添付](../cpp/bstr-t-attach.md)|`_bstr_t` ラッパーを `BSTR` にリンクします。|  
|[copy](../cpp/bstr-t-copy.md)|カプセル化された `BSTR` のコピーを生成します。|  
|[デタッチ](../cpp/bstr-t-detach.md)|`BSTR` でラップされた `_bstr_t` を返し、`BSTR` から `_bstr_t` をデタッチします。|  
|[GetAddress](../cpp/bstr-t-getaddress.md)|`BSTR` でラップされた `_bstr_t` を指します。|  
|[GetBSTR](../cpp/bstr-t-getbstr.md)|`BSTR` でラップされた `_bstr_t` の先頭を指します。|  
|[length](../cpp/bstr-t-length.md)|`_bstr_t` の文字数を返します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 =](../cpp/bstr-t-operator-equal.md)|既存の `_bstr_t` オブジェクトに新しい値を代入します。|  
|[operator + =](../cpp/bstr-t-operator-add-equal-plus.md)|`_bstr_t` の末尾に文字を追加します。|  
|[演算子 +](../cpp/bstr-t-operator-add-equal-plus.md)|2 つの文字列を連結します。|  
|[演算子 !](../cpp/bstr-t-operator-logical-not.md)|場合にチェック カプセル化された`BSTR`は、NULL 文字列です。|  
|[演算子 = =、! =、 \<、>、 \<=、> =](../cpp/bstr-t-relational-operators.md)|2 つの `_bstr_t` オブジェクトを比較します。|  
|[演算子 wchar_t * &#124; char\*](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)|カプセル化された Unicode またはマルチバイト `BSTR` オブジェクトへのポインターを抽出します。|  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<comutil.h >  
  
 **Lib:** comsuppw.lib または comsuppwd.lib (を参照してください[/Zc:wchar_t (wchar_t をネイティブ型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)詳細)  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)