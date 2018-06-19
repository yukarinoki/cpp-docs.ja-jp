---
title: '&lt;exception&gt; typedefs | Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- exception/std::exception_ptr
- exception/std::terminate_handler
- exception/std::unexpected_handler
ms.assetid: 2a338480-35e2-46f7-b223-52d4e84a5768
ms.openlocfilehash: 68f95407fe22c7e8b70426e555f46eb0a4c80338
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33846260"
---
# <a name="ltexceptiongt-typedefs"></a>&lt;exception&gt; typedefs

||||
|-|-|-|
|[exception_ptr](#exception_ptr)|[terminate_handler](#terminate_handler)|[unexpected_handler](#unexpected_handler)|

## <a name="exception_ptr"></a>  exception_ptr

例外へのポインターを表す型。

```cpp
typedef unspecified exception_ptr;
```

### <a name="remarks"></a>コメント

`exception_ptr` 型を実装するために使用される未指定の内部クラス。

現在の例外またはユーザーが指定した例外のインスタンスを参照するには、`exception_ptr` オブジェクトを使用します。 Microsoft の実装では、例外は [EXCEPTION_RECORD](http://msdn.microsoft.com/library/windows/desktop/aa363082) 構造体によって表されます。 各 `exception_ptr` オブジェクトには、例外を表す `EXCEPTION_RECORD` 構造体のコピーを指す例外参照フィールドが含まれています。

`exception_ptr` 変数を宣言する場合、変数は例外に関連付けられません。 つまり、例外参照フィールドが NULL です。 このような `exception_ptr` オブジェクトは、*null exception_ptr* と呼ばれます。

例外を `current_exception` オブジェクトに割り当てるには、`make_exception_ptr` または `exception_ptr` 関数を使用します。 `exception_ptr` 変数に例外を割り当てた場合、変数の例外参照フィールドは例外のコピーを指します。 例外をコピーするためのメモリが不足している場合、例外参照フィールドは、[std::bad_alloc](../standard-library/bad-alloc-class.md) 例外のコピーを指し示します。 `current_exception` 関数または `make_exception_ptr` 関数が他の理由で例外をでコピーできない場合、この関数は、現在のプロセスを終了する **terminate** CRT 関数を呼び出します。

名前とは異なり、`exception_ptr` オブジェクト自体はポインターではありません。 ポインターのセマンティクスに従わず、ポインターのメンバー アクセス (`->`) 演算子または間接 (*) 演算子で使用することはできません。 `exception_ptr` オブジェクトには、パブリック データ メンバーまたはメンバー関数がありません。

**比較:**

等値演算子 (`==`) と不等値演算子 (`!=`) を使用して、2 種類の `exception_ptr` オブジェクトを比較できます。 演算子は、例外を表す `EXCEPTION_RECORD` 構造体のバイナリ値 (ビット パターン) は比較しません。 代わりに、演算子は `exception_ptr` オブジェクトの例外参照フィールドのアドレスを比較します。 その結果、null `exception_ptr` と NULL 値を比較すると、等しいと評価されます。

## <a name="terminate_handler"></a>  terminate_handler

この型は、`terminate_handler` として使用するのに適した関数へのポインターを表します。

```cpp
typedef void (*terminate_handler)();
```

### <a name="remarks"></a>コメント

この型は、終了ハンドラーとして使用するのに適した関数へのポインターを表します。

### <a name="example"></a>例

`terminate_handler` の使用例については、「[set_terminate](../standard-library/exception-functions.md#set_terminate)」を参照してください。

## <a name="unexpected_handler"></a>  unexpected_handler

この型は、`unexpected_handler` として使用するのに適した関数へのポインターを表します。

```cpp
typedef void (*unexpected_handler)();
```

### <a name="example"></a>例

`unexpected_handler` の使用例については、「[set_unexpected](../standard-library/exception-functions.md#set_unexpected)」を参照してください。

## <a name="see-also"></a>関連項目

[\<exception>](../standard-library/exception.md)<br/>
