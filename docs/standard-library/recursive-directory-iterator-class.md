---
description: '詳細情報: recursive_directory_iterator クラス'
title: recursive_directory_iterator クラス
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
ms.openlocfilehash: b9b5909c62a745233362eeac1adb879c1585098c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337908"
---
# <a name="recursive_directory_iterator-class"></a>recursive_directory_iterator クラス

ディレクトリ内のファイル名をシーケンス処理する入力反復子を記述します。再帰的にサブディレクトリに向かって降順に並べ替えます。 反復子の場合 `X` 、式は、 `*X` `directory_entry` ファイル名をラップするクラスのオブジェクトと、その状態に関する既知のものに評価されます。

詳細とコード例については、「 [ファイルシステムのナビゲーション (C++)](../standard-library/file-system-navigation.md)」を参照してください。

## <a name="syntax"></a>構文

```cpp
class recursive_directory_iterator;
```

## <a name="remarks"></a>解説

クラステンプレートには、次のものが格納されます。

1. `stack<pair<directory_iterator, path>>` `mystack` シーケンスされるディレクトリの入れ子を表す、exposition の目的でここで呼び出される型のオブジェクト。

1. ここで呼び出される型のオブジェクト。 `directory_entry` `myentry` ディレクトリシーケンス内の現在のファイル名を表します。

1. **`bool`** `no_push` サブディレクトリへの再帰降下が無効になっているかどうかを記録する、型のオブジェクト。ここで呼び出されます。

1. `directory_options`ここで呼び出され、 `myoptions` 構築時に確立されたオプションを記録する型のオブジェクト。

型の既定の構築されたオブジェクトは、 `recursive_directory_entry` でシーケンスの末尾の反復子を持ち、 `mystack.top().first` シーケンスの末尾の反復子を表します。 たとえば、ディレクトリにエントリ (ディレクトリ)、、およびが指定されている場合、 `abc` `def` `def/ghi` `jkl` コードは次のようになります。

```cpp
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)
    visit(next->path());
```

は、引数とを使用して visit を呼び出し `path("abc/def/ghi")` `path("abc/jkl")` ます。 ディレクトリサブツリーの順序付けは、次の2つの方法で修飾できます。

1. ディレクトリシンボリックリンクは、値がである引数を使用してを構築する場合にのみスキャンされ `recursive_directory_iterator` `directory_options` `directory_options::follow_directory_symlink` ます。

1. を呼び出すと、 `disable_recursion_pending` インクリメント中に発生した後続のディレクトリは再帰的にスキャンされません。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[recursive_directory_iterator](#recursive_directory_iterator)|`recursive_directory_iterator` を構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[デプス](#depth)|はを返し `mystack.size() - 1` ます。したがって、 `pval` は深度0になります。|
|[disable_recursion_pending](#disable_recursion_pending)|に格納さ **`true`** `no_push` れます。|
|[increment](#increment)|は、次のファイル名に順に進みます。|
|[options](#options)|`myoptions` が返されます。|
|[ショート](#pop)|次のオブジェクトを返します。|
|[recursion_pending](#recursion_pending)|`!no_push` が返されます。|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[operator! =](#op_neq)|`!(*this == right)` が返されます。|
|[operator =](#op_as)|この既定のメンバー代入演算子は想定どおりに動作します。|
|[operator = =](#op_eq)|**`true`** との両方 **`*this`** がシーケンス末尾の反復子であるか、両方がシーケンスの末尾の反復子でない場合にのみ、を返します。|
|[operator](#op_multiply)|`myentry` が返されます。|
|[演算子->](#op_cast)|`&**this` が返されます。|
|[+ + 演算子](#op_increment)|をインクリメント `recursive_directory_iterator` します。|

## <a name="requirements"></a>要件

**ヘッダー:**\<filesystem>

**名前空間:** std::tr2::sys

## <a name="recursive_directory_iteratordepth"></a><a name="depth"></a> recursive_directory_iterator::d epth

はを返し `mystack.size() - 1` ます。したがって、 `pval` は深度0になります。

```cpp
int depth() const;
```

## <a name="recursive_directory_iteratordisable_recursion_pending"></a><a name="disable_recursion_pending"></a> recursive_directory_iterator::d isable_recursion_pending

に格納さ **`true`** `no_push` れます。

```cpp
void disable_recursion_pending();
```

## <a name="recursive_directory_iteratorincrement"></a><a name="increment"></a> recursive_directory_iterator:: increment

は、次のファイル名に順に進みます。

```cpp
recursive_directory_iterator& increment(error_code& ec) noexcept;
```

### <a name="parameters"></a>パラメーター

*c*\
指定されたエラーコードです。

### <a name="remarks"></a>解説

この関数は、ネストされたシーケンス内の次のファイル名に進もうとします。 成功した場合は、そのファイル名をに格納します。それ以外の場合は、 `myentry` シーケンス末尾の反復子を生成します。

## <a name="recursive_directory_iteratoroperator"></a><a name="op_neq"></a> recursive_directory_iterator:: operator! =

`!(*this == right)` が返されます。

```cpp
bool operator!=(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>パラメーター

*そうです*\
比較対象の [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) 。

## <a name="recursive_directory_iteratoroperator"></a><a name="op_as"></a> recursive_directory_iterator:: operator =

この既定のメンバー代入演算子は想定どおりに動作します。

```cpp
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>パラメーター

*recursive_directory_iterator*\
にコピーされる [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) `recursive_directory_iterator` 。

## <a name="recursive_directory_iteratoroperator"></a><a name="op_eq"></a> recursive_directory_iterator:: operator = =

**`true`** との両方 **`*this`** がシーケンス末尾の反復子であるか、両方がシーケンスの末尾の反復子でない場合にのみ、を返します。

```cpp
bool operator==(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>パラメーター

*そうです*\
比較対象の [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) 。

## <a name="recursive_directory_iteratoroperator"></a><a name="op_multiply"></a> recursive_directory_iterator:: operator *

`myentry` が返されます。

```cpp
const directory_entry& operator*() const;
```

## <a name="recursive_directory_iteratoroperator-"></a><a name="op_cast"></a> recursive_directory_iterator:: operator->

`&**this` が返されます。

```cpp
const directory_entry * operator->() const;
```

## <a name="recursive_directory_iteratoroperator"></a><a name="op_increment"></a> recursive_directory_iterator:: operator + +

をインクリメント `recursive_directory_iterator` します。

```cpp
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```

### <a name="parameters"></a>パラメーター

*通り*\
指定されたインクリメント。

### <a name="remarks"></a>解説

最初のメンバー関数は `increment()` を呼び出し、を返し **`*this`** ます。 2番目のメンバー関数は、オブジェクトのコピーを作成して `increment()` を呼び出し、そのコピーを返します。

## <a name="recursive_directory_iteratoroptions"></a><a name="options"></a> recursive_directory_iterator:: options

`myoptions` が返されます。

```cpp
directory_options options() const;
```

## <a name="recursive_directory_iteratorpop"></a><a name="pop"></a> recursive_directory_iterator::p op

次のオブジェクトを返します。

```cpp
void pop();
```

### <a name="remarks"></a>解説

`depth() == 0`オブジェクトがシーケンス末尾の反復子になる場合は。 そうでない場合、メンバー関数は現在の (最も深い) ディレクトリのスキャンを中断し、1 つ下の深さから再開します。

## <a name="recursive_directory_iteratorrecursion_pending"></a><a name="recursion_pending"></a> recursive_directory_iterator:: recursion_pending

`!no_push` が返されます。

```cpp
bool recursion_pending() const;
```

## <a name="recursive_directory_iteratorrecursive_directory_iterator"></a><a name="recursive_directory_iterator"></a> recursive_directory_iterator:: recursive_directory_iterator

`recursive_directory_iterator` を構築します。

```cpp
recursive_directory_iterator() noexcept;
explicit recursive_directory_iterator(const path& pval);

recursive_directory_iterator(const path& pval,
    error_code& ec) noexcept;
recursive_directory_iterator(const path& pval,
    directory_options opts);

recursive_directory_iterator(const path& pval,
    directory_options opts,
    error_code& ec) noexcept;
recursive_directory_iterator(const recursive_directory_iterator&) = default;
recursive_directory_iterator(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>パラメーター

*pval*\
指定するパス。

*error_code*\
指定されたエラーコード。

*受ける*\
指定されたディレクトリオプション。

*recursive_directory_iterator*\
構築された `recursive_directory_iterator` のコピー元となる `recursive_directory_iterator`。

### <a name="remarks"></a>解説

1 つ目のコンストラクターは、end-of-sequence 反復子を生成します。 2番目と3番目のコンストラクターは、とにを格納し **`false`** `no_push` `directory_options::none` `myoptions` 、 *pval* をディレクトリとして開き、読み取りを試みます。 成功した場合、 `mystack` `myentry` 入れ子になったシーケンス内の最初の非ディレクトリファイル名を初期化して指定します。それ以外の場合は、シーケンス末尾の反復子を生成します。

4番目と5番目のコンストラクターは、最初に optin *を格納する* 点を除いて、2番目と3番目のコンストラクターと同じように動作し `myoptions` ます。 既定のコンストラクターは想定どおりの動作をします。

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem>](../standard-library/filesystem.md)\
[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)
