---
title: '&lt;exception&gt; | Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <exception>
dev_langs:
- C++
helpviewer_keywords:
- exception header
ms.assetid: 28900768-5dd7-4834-b907-5e37ab3407db
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbd57085225bb21b9f7ce8bd34c537d3bc414797
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845818"
---
# <a name="ltexceptiongt"></a>&lt;exception&gt;

例外の処理に関連する型と関数を定義します。 例外処理は、システムがエラーから回復できる場合に使用されます。 例外処理では、関数からプログラムへ制御を返すための方法を利用できます。 例外処理を組み込む目的は、規則的な手順でエラーから回復する方法を実施して、プログラムの信頼性を向上させることです。

## <a name="syntax"></a>構文

```cpp
#include <exception>

```

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)|例外へのポインターを表す型。|
|[terminate_handler](../standard-library/exception-typedefs.md#terminate_handler)|`terminate_handler` として使用するのに適した関数へのポインターを表す型。|
|[unexpected_handler](../standard-library/exception-typedefs.md#unexpected_handler)|`unexpected_handler` として使用するのに適した関数へのポインターを表す型。|

### <a name="functions"></a>関数

|関数|説明|
|-|-|
|[current_exception](../standard-library/exception-functions.md#current_exception)|現在の例外へのポインターを取得します。|
|[get_terminate](../standard-library/exception-functions.md#get_terminate)|現在の `terminate_handler` 関数を取得します。|
|[get_unexpected](../standard-library/exception-functions.md#get_unexpected)|現在の `unexpected_handler` 関数を取得します。|
|[make_exception_ptr](../standard-library/exception-functions.md#make_exception_ptr)|例外のコピーを保持する `exception_ptr` オブジェクトを作成します。|
|[rethrow_exception](../standard-library/exception-functions.md#rethrow_exception)|パラメーターとして渡された例外をスローします。|
|[set_terminate](../standard-library/exception-functions.md#set_terminate)|プログラムの終了時に呼び出される新しい `terminate_handler` を設定します。|
|[set_unexpected](../standard-library/exception-functions.md#set_unexpected)|予期しない例外が発生したときに新しい `unexpected_handler` が存在するように設定します。|
|[terminate](../standard-library/exception-functions.md#terminate)|終了ハンドラーを呼び出します。|
|[uncaught_exception](../standard-library/exception-functions.md#uncaught_exception)|スローされた例外が現在処理されている場合にのみ **true** を返します。|
|[unexpected](../standard-library/exception-functions.md#unexpected)|予期しないハンドラーを呼び出します。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[bad_exception クラス](../standard-library/bad-exception-class.md)|このクラスは、`unexpected_handler` からスローされる例外を記述します。|
|[exception クラス](../standard-library/exception-class.md)|このクラスは、特定の式と C++ 標準ライブラリによってスローされたすべての例外の基底クラスとして機能します。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
