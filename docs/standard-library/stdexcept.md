---
title: '&lt;stdexcept&gt;'
ms.date: 11/04/2016
f1_keywords:
- <stdexcept>
helpviewer_keywords:
- stdexcept header
ms.assetid: 495c10b1-1e60-4514-9f8f-7fda11a2f522
ms.openlocfilehash: 8a8c99f2651d10d4fc2aff413a06256127f32d7d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412502"
---
# <a name="ltstdexceptgt"></a>&lt;stdexcept&gt;

例外の通知に使用する複数の標準クラスを定義します。 このクラスは、[exception](../standard-library/exception-class.md) クラスから派生したものからなる派生階層を形成します。このクラスには、論理エラーと実行時エラーという 2 種類の一般的な例外の型が含まれます。 論理エラーはプログラマの誤りが原因で発生します。 これらは、基底クラス logic_error から派生します。

- `domain_error`

- `invalid_argument`

- `length_error`

- `out_of_range`

実行時エラーは、ライブラリ関数か実行時のシステムの誤りが原因で発生します。 これらは、基底クラス runtime_error から派生し、次のものが含まれます。

- `overflow_error`

- `range_error`

- `underflow_error`

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[domain_error クラス](../standard-library/domain-error-class.md)|このクラスは、ドメイン エラーを通知するためにスローされる例外すべてに対する基底クラスとして機能します。|
|[invalid_argument クラス](../standard-library/invalid-argument-class.md)|このクラスは、無効な引数を通知するためにスローされる例外すべてに対する基底クラスとして機能します。|
|[length_error クラス](../standard-library/length-error-class.md)|このクラスは、生成を試みたオブジェクトが長すぎて指定できないことを通知するためにスローされる例外すべてに対する基底クラスとして機能します。|
|[logic_error クラス](../standard-library/logic-error-class.md)|このクラスは、論理的前提条件に対する違反など、プログラムの実行前に検出可能なエラーを通知するためにスローされる例外すべてに対する基底クラスとして機能します。|
|[out_of_range クラス](../standard-library/out-of-range-class.md)|このクラスは、有効範囲外の引数を通知するためにスローされる例外すべてに対する基底クラスとして機能します。|
|[overflow_error クラス](../standard-library/overflow-error-class.md)|このクラスは、算術オーバーフローを通知するためにスローされる例外すべてに対する基底クラスとして機能します。|
|[range_error クラス](../standard-library/range-error-class.md)|このクラスは、範囲のエラーを通知するためにスローされる例外すべてに対する基底クラスとして機能します。|
|[runtime_error クラス](../standard-library/runtime-error-class.md)|このクラスは、プログラムの実行時にのみ検出可能なエラーを通知するためにスローされる例外すべてに対する基底クラスとして機能します。|
|[underflow_error クラス](../standard-library/underflow-error-class.md)|このクラスは、算術アンダーフローを通知するためにスローされる例外すべてに対する基底クラスとして機能します。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
