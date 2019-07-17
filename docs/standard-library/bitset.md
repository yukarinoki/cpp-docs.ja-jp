---
title: '&lt;bitset&gt;'
ms.date: 11/04/2016
f1_keywords:
- <bitset>
helpviewer_keywords:
- <bitset> header
- bitset header
ms.assetid: af30a9b9-489e-46e3-9d29-5f3ea07ae6dc
ms.openlocfilehash: b0a5a01ca04d01d9535291e3c4a254143bc09e5a
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68243300"
---
# <a name="ltbitsetgt"></a>&lt;bitset&gt;

ビットの固定サイズ シーケンスを表して処理するための、テンプレート クラス ビットセットと 2 つのサポート テンプレート関数を定義します。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<bitset>

**名前空間:** std

## <a name="members"></a>メンバー

### <a name="operators"></a>演算子

|||
|-|-|
|[operator&](../standard-library/bitset-operators.md#op_amp)|次の 2 つのビットセット間でビットごとの AND を実行します。|
|[operator<\<](../standard-library/bitset-operators.md#op_lt_lt)|ビット シーケンスのテキスト表現を標準出力ストリームに挿入します。|
|[operator>>](../standard-library/bitset-operators.md#op_gt_gt)|ビット シーケンスのテキスト表現を標準入力ストリームに挿入します。|
|[operator^](../standard-library/bitset-operators.md#op_xor)|次の 2 つのビットセット間でビットごとの EXCLUSIVE-OR を実行します。|
|[operator&#124;](../standard-library/bitset-operators.md#op_or)|次の 2 つのビットセット間でビットごとの OR を実行します。|

### <a name="classes"></a>クラス

|||
|-|-|
|[bitset](../standard-library/bitset-class.md)|このテンプレート クラスは、固定数のビットで構成されるシーケンスを格納するオブジェクト型を記述します。これらのビットによって、一連の項目または条件のフラグを保持するためのコンパクトな方法が提供されます。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
