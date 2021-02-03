---
title: _bstr_t クラス
description: '詳細情報: _bstr_t クラス'
ms.date: 02/02/2021
f1_keywords:
- _bstr_t
helpviewer_keywords:
- BSTR object
- _bstr_t class
- BSTR object [C++], COM encapsulation
ms.openlocfilehash: 71f5f0a27989b416cf4f13873254890db09ce334
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522873"
---
# <a name="_bstr_t-class"></a>`_bstr_t` クラス

**Microsoft 固有の仕様**

`_bstr_t`オブジェクトは、 [BSTR データ型](/previous-versions/windows/desktop/automat/bstr)をカプセル化します。 クラスは、およびなどの api への関数呼び出しによってリソースの割り当てと解放を管理し [`SysAllocString`](/windows/win32/api/oleauto/nf-oleauto-sysallocstring) [`SysFreeString`](/windows/win32/api/oleauto/nf-oleauto-sysfreestring) `BSTR` ます。 クラスは、 `_bstr_t` 過剰なオーバーヘッドを避けるために、参照カウントを使用します。

## <a name="members"></a>メンバー

### <a name="construction"></a>建設

| コンストラクター | 説明 |
|--|--|
| [`_bstr_t`](../cpp/bstr-t-bstr-t.md) | `_bstr_t` オブジェクトを構築します。 |

### <a name="operations"></a>Operations

| 機能 | [説明] |
|--|--|
| [`Assign`](../cpp/bstr-t-assign.md) | `BSTR` を `BSTR` でラップされた `_bstr_t` にコピーします。 |
| [`Attach`](../cpp/bstr-t-attach.md) | `_bstr_t` ラッパーを `BSTR` にリンクします。 |
| [`copy`](../cpp/bstr-t-copy.md) | カプセル化された `BSTR` のコピーを生成します。 |
| [`Detach`](../cpp/bstr-t-detach.md) | `BSTR` でラップされた `_bstr_t` を返し、`BSTR` から `_bstr_t` をデタッチします。 |
| [`GetAddress`](../cpp/bstr-t-getaddress.md) | `BSTR` でラップされた `_bstr_t` を指します。 |
| [`GetBSTR`](../cpp/bstr-t-getbstr.md) | `BSTR` でラップされた `_bstr_t` の先頭を指します。 |
| [`length`](../cpp/bstr-t-length.md) | `_bstr_t` の文字数を返します。 |

### <a name="operators"></a>演算子

| 演算子 | [説明] |
|--|--|
| [`operator =`](../cpp/bstr-t-operator-equal.md) | 既存の `_bstr_t` オブジェクトに新しい値を代入します。 |
| [`operator +=`](../cpp/bstr-t-operator-add-equal-plus.md) | `_bstr_t` の末尾に文字を追加します。 |
| [`operator +`](../cpp/bstr-t-operator-add-equal-plus.md) | 2 つの文字列を連結します。 |
| [`operator !`](../cpp/bstr-t-operator-logical-not.md) | カプセル化されたが NULL 文字列であるかどうかを確認 `BSTR` します。 |
| [`operator ==`](../cpp/bstr-t-relational-operators.md)<br/>[`operator !=`](../cpp/bstr-t-relational-operators.md)<br/>[`operator <`](../cpp/bstr-t-relational-operators.md)<br/>[`operator >`](../cpp/bstr-t-relational-operators.md)<br/>[`operator <=`](../cpp/bstr-t-relational-operators.md)<br/>[`operator >=`](../cpp/bstr-t-relational-operators.md) | 2 つの `_bstr_t` オブジェクトを比較します。 |
| [`operator wchar_t*`](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)<br/>[`operator char*`](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)  | カプセル化された Unicode またはマルチバイト `BSTR` オブジェクトへのポインターを抽出します。 |

**Microsoft 固有の仕様はここまで**

## <a name="requirements"></a>要件

**ヘッダー:**\<comutil.h>

**Lib:** *`comsuppw.lib`* または *`comsuppwd.lib`* (詳細については、「 [ `/Zc:wchar_t` (wchar_t はネイティブ型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)」を参照してください)。

## <a name="see-also"></a>関連項目

[コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)
