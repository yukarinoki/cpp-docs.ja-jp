---
title: _bstr_t クラス
ms.date: 11/04/2016
f1_keywords:
- _bstr_t
helpviewer_keywords:
- BSTR object
- _bstr_t class
- BSTR object [C++], COM encapsulation
ms.assetid: 58841fef-fe21-4a84-aab9-780262b5201f
ms.openlocfilehash: 3ef89c6f6742d528c427c49fd2a62d8820625e79
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190379"
---
# <a name="_bstr_t-class"></a>_bstr_t クラス

**Microsoft 固有の仕様**

`_bstr_t` オブジェクトは、 [BSTR データ型](/previous-versions/windows/desktop/automat/bstr)をカプセル化します。 クラスは、必要に応じて `SysAllocString` と `SysFreeString` およびその他の `BSTR` Api への関数呼び出しによって、リソースの割り当てと割り当て解除を管理します。 **_Bstr_t**クラスは、過剰なオーバーヘッドを避けるために参照カウントを使用します。

### <a name="construction"></a>構築

|||
|-|-|
|[_bstr_t](../cpp/bstr-t-bstr-t.md)|`_bstr_t` オブジェクトを構築します。|

### <a name="operations"></a>操作

|||
|-|-|
|[Assign](../cpp/bstr-t-assign.md)|`BSTR` を `BSTR` でラップされた `_bstr_t` にコピーします。|
|[[アタッチ]](../cpp/bstr-t-attach.md)|`_bstr_t` ラッパーを `BSTR` にリンクします。|
|[copy](../cpp/bstr-t-copy.md)|カプセル化された `BSTR` のコピーを生成します。|
|[[デタッチ]](../cpp/bstr-t-detach.md)|`BSTR` でラップされた `_bstr_t` を返し、`BSTR` から `_bstr_t` をデタッチします。|
|[GetAddress](../cpp/bstr-t-getaddress.md)|`BSTR` でラップされた `_bstr_t` を指します。|
|[GetBSTR](../cpp/bstr-t-getbstr.md)|`BSTR` でラップされた `_bstr_t` の先頭を指します。|
|[length](../cpp/bstr-t-length.md)|`_bstr_t` の文字数を返します。|

### <a name="operators"></a>オペレーター

|||
|-|-|
|[operator =](../cpp/bstr-t-operator-equal.md)|既存の `_bstr_t` オブジェクトに新しい値を代入します。|
|[演算子 + =](../cpp/bstr-t-operator-add-equal-plus.md)|`_bstr_t` の末尾に文字を追加します。|
|[演算子 +](../cpp/bstr-t-operator-add-equal-plus.md)|2 つの文字列を連結します。|
|[演算子 !](../cpp/bstr-t-operator-logical-not.md)|カプセル化された `BSTR` が NULL 文字列であるかどうかを確認します。|
|[operator = =、! =、\<、>、\<=、> =](../cpp/bstr-t-relational-operators.md)|2 つの `_bstr_t` オブジェクトを比較します。|
|[operator wchar_t * &#124; char\*](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)|カプセル化された Unicode またはマルチバイト `BSTR` オブジェクトへのポインターを抽出します。|

**Microsoft 固有の仕様はここまで**

## <a name="requirements"></a>必要条件

**ヘッダー:** \<comutil. h >

**Lib:** comsuppw または comsuppw (詳細について[は、「/zc: Wchar_t (wchar_t ネイティブ型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 」を参照してください)

## <a name="see-also"></a>参照

[コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)
