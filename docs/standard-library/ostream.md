---
description: '詳細情報: &lt; ostream&gt;'
title: '&lt;ostream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <ostream>
helpviewer_keywords:
- ostream header
ms.assetid: 90c3b6fb-57cd-4ae7-99b8-8512f24a67d2
ms.openlocfilehash: a31ffe801fca16e3b7fc1037c59613150e383933
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126430"
---
# <a name="ltostreamgt"></a>&lt;ostream&gt;

Iostreams の挿入を仲介するクラステンプレート [basic_ostream](../standard-library/basic-ostream-class.md)を定義します。 ヘッダーは、関連する複数のマニピュレーターを定義します  (通常このヘッダーは、別の iostream ヘッダーに含まれています。 まれに、直接含めなければならないことがあります)。

## <a name="syntax"></a>構文

```cpp
#include <ostream>
```

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[ostream](../standard-library/ostream-typedefs.md#ostream)|で特殊化された型をから作成し `basic_ostream` **`char`** `char_traits` **`char`** ます。|
|[wostream](../standard-library/ostream-typedefs.md#wostream)|で特殊化された型をから作成し `basic_ostream` **`wchar_t`** `char_traits` **`wchar_t`** ます。|

### <a name="manipulators"></a>マニピュレーター

|名前|説明|
|-|-|
|[endl](../standard-library/ostream-functions.md#endl)|行を終了し、バッファーをフラッシュします。|
|[端](../standard-library/ostream-functions.md#ends)|文字列を終了します。|
|[揃える](../standard-library/ostream-functions.md#flush)|バッファーをフラッシュします。|
|[スワップ](../standard-library/ostream-functions.md#swap)|左側の `basic_ostream` オブジェクト パラメーターの値と右側の `basic_ostream` オブジェクト パラメーターの値を交換します。|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[<<演算子 ](../standard-library/ostream-operators.md#op_lt_lt)|さまざまな型をストリームに書き込みます。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[basic_ostream](../standard-library/basic-ostream-class.md)|クラステンプレートは、要素とエンコードされたオブジェクトのストリームバッファーへの挿入を制御するオブジェクトを表します。|

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[iostreams の規則](../standard-library/iostreams-conventions.md)
