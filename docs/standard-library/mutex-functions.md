---
title: '&lt;mutex&gt; 関数および変数'
ms.date: 11/04/2016
f1_keywords:
- mutex/std::adopt_lock
- mutex/std::call_once
- mutex/std::defer_lock
- mutex/std::lock
- mutex/std::try_to_lock
ms.assetid: 78ab3c8b-c7db-4226-ac93-e2e78ff8b964
helpviewer_keywords:
- std::adopt_lock [C++]
- std::call_once [C++]
- std::defer_lock [C++]
- std::lock [C++]
- std::try_to_lock [C++]
ms.openlocfilehash: b375aec0bee4183563b8cd55e4e8a27f79e7cd3e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326327"
---
# <a name="ltmutexgt-functions-and-variables"></a>&lt;mutex&gt; 関数および変数

||||
|-|-|-|
|[adopt_lock](#adopt_lock)|[call_once](#call_once)|[defer_lock](#defer_lock)|
|[lock](#lock)|[try_to_lock](#try_to_lock)|

## <a name="adopt_lock"></a>  adopt_lock 関数

[lock_guard](../standard-library/lock-guard-class.md) と [unique_lock](../standard-library/unique-lock-class.md) のコンストラクターに渡されるオブジェクトを表し、同じコンストラクターに渡されるミューテックス オブジェクトがロックされていることを示します。

```cpp
const adopt_lock_t adopt_lock;
```

## <a name="call_once"></a>  call_once

指定された呼び出し可能オブジェクトが、実行中に 1 回だけ呼び出されるメカニズムを提供します。

```cpp
template <class Callable, class... Args>
void call_once(once_flag& Flag,
    Callable F&&, Args&&... A);
```

### <a name="parameters"></a>パラメーター

*フラグ*<br/>
呼び出し可能オブジェクトが 1 回だけ呼び出されるようにする [once_flag](../standard-library/once-flag-structure.md) オブジェクト。

*F*<br/>
呼び出し可能オブジェクト。

*A*<br/>
引数リスト。

### <a name="remarks"></a>Remarks

場合*フラグ*が無効ですが、関数、 [system_error](../standard-library/system-error-class.md)のエラー コードを持つ`invalid_argument`します。 それ以外の場合、テンプレート関数を使用してその*フラグ*を呼び出していることを確認する引数`F(A...)`回数にかかわらずが 1 回だけにテンプレート関数が呼び出されます。 `F(A...)` が例外をスローして終了した場合、呼び出しは失敗です。

## <a name="defer_lock"></a>  defer_lock 変数

[unique_lock](../standard-library/unique-lock-class.md) のコンストラクターに渡すことができるオブジェクトを表します。 これは、コンストラクターに渡される mitex オブジェクトをコンストラクターがロックしてはならないことを示します。

```cpp
const defer_lock_t defer_lock;
```

## <a name="lock"></a>  lock

デッドロックなしですべての引数をロックしようとします。

```cpp
template <class L1, class L2, class... L3>
void lock(L1&, L2&, L3&...);
```

### <a name="remarks"></a>Remarks

このテンプレート関数に対する引数は、例外をスローする可能性がある `try_lock` への呼び出しを除いて、*mutex 型*である必要があります。

この関数は、`lock`、`try_lock`、および `unlock` への呼び出しによるデッドロックなしで、すべての引数をロックします。 `lock` または `try_lock` の呼び出しで例外がスローされると、この関数は再び例外をスローする前に正常にロックされた mutex オブジェクトのいずれかに `unlock` を呼び出します。

## <a name="try_to_lock"></a>  try_to_lock 変数

[unique_lock](../standard-library/unique-lock-class.md) のコンストラクターに渡すことのできるオブジェクトを表し、ブロックされずに渡される `mutex` をコンストラクターがロック解除しようとしたほうがよいことを示します。

```cpp
const try_to_lock_t try_to_lock;
```

## <a name="see-also"></a>関連項目

[\<mutex>](../standard-library/mutex.md)<br/>
