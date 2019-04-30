---
title: recursive_directory_iterator クラス
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
ms.openlocfilehash: 52e6f738aa226dba26bae0cf6e97cd18d107d677
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370132"
---
# <a name="recursivedirectoryiterator-class"></a>recursive_directory_iterator クラス

入力反復子のディレクトリにファイル名を走査する可能性がある再帰的にサブディレクトリ降順をについて説明します。 反復子のため`X`、式`*X`クラスのオブジェクトを指す`directory_entry`ファイル名とその状態に関する既知の情報をラップします。

詳細およびコード例については、「[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)」を参照してください。

## <a name="syntax"></a>構文

```cpp
class recursive_directory_iterator;
```

## <a name="remarks"></a>Remarks

テンプレート クラスは以下を格納します。

1. 型のオブジェクト`stack<pair<directory_iterator, path>>`という`mystack`シーケンス処理するディレクトリのネストを表す説明のためには、ここで

1. 型のオブジェクト`directory_entry`と呼ばれる`myentry`ここでは、ディレクトリ シーケンス内の現在のファイル名を表します

1. 型のオブジェクト**bool**という`no_push`ここでは、サブディレクトリへの再帰ディセントが無効になっているかどうかを記録します。

1. 型のオブジェクト`directory_options`という`myoptions`ここでは、構築時に設定されたオプションを記録します。

型の既定で構築されるオブジェクト`recursive_directory_entry`でシーケンス末尾の反復子のある`mystack.top().first`シーケンス末尾の反復子を表します。 たとえば、ディレクトリを指定`abc`エントリを含む`def`(ディレクトリ) `def/ghi`、および`jkl`コード。

```cpp
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)
    visit(next->path());
```

引数を使用して visit を呼び出します`path("abc/def/ghi")`と`path("abc/jkl")`します。 2 つの方法でディレクトリ サブツリーの走査を修飾することができます。

1. 構築する場合にのみ、ディレクトリ symlink がスキャンされます、`recursive_directory_iterator`で、`directory_options`引数の値が`directory_options::follow_directory_symlink`します。

1. 呼び出す場合`disable_recursion_pending`インクリメント中に発生した後続ディレクトリは再帰的にスキャンができません。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[recursive_directory_iterator](#recursive_directory_iterator)|`recursive_directory_iterator` を構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[深さ](#depth)|返します`mystack.size() - 1`ため、`pval`深さ 0 です。|
|[disable_recursion_pending](#disable_recursion_pending)|ストア**true**で`no_push`します。|
|[increment](#increment)|シーケンス内の次のファイル名に進みます。|
|[options](#options)|`myoptions` を返します。|
|[pop](#pop)|次のオブジェクトを返します。|
|[recursion_pending](#recursion_pending)|`!no_push` を返します。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator!=](#op_neq)|`!(*this == right)` を返します。|
|[operator=](#op_as)|この既定のメンバー代入演算子は想定どおりに動作します。|
|[operator==](#op_eq)|返します**true**両方の場合にのみ`*this`と*右*シーケンス末尾の反復子またはその両方がないエンド-の-シーケンスの反復子。|
|[operator*](#op_multiply)|`myentry` を返します。|
|[operator->](#op_cast)|`&**this` を返します。|
|[operator++](#op_increment)|インクリメント、`recursive_directory_iterator`します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<filesystem >

**名前空間:** std::tr2::sys

## <a name="depth"></a> recursive_directory_iterator::depth

返します`mystack.size() - 1`ため、`pval`深さ 0 です。

```cpp
int depth() const;
```

## <a name="disable_recursion_pending"></a> recursive_directory_iterator::disable_recursion_pending

ストア**true**で`no_push`します。

```cpp
void disable_recursion_pending();
```

## <a name="increment"></a> recursive_directory_iterator::increment

シーケンス内の次のファイル名に進みます。

```cpp
recursive_directory_iterator& increment(error_code& ec) noexcept;
```

### <a name="parameters"></a>パラメーター

*ec*<br/>
エラー コードを指定します。

### <a name="remarks"></a>Remarks

この関数は、ネストされたシーケンス内の次のファイル名に進もうとします。 かどうかは成功すると、そのファイル名を格納で`myentry`。 それ以外の場合、シーケンス末尾の反復子が生成されます。

## <a name="op_neq"></a> recursive_directory_iterator::operator! =

`!(*this == right)` を返します。

```cpp
bool operator!=(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>パラメーター

*right*<br/>
[Recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md)比較します。

## <a name="op_as"></a> recursive_directory_iterator::operator =

この既定のメンバー代入演算子は想定どおりに動作します。

```cpp
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>パラメーター

*recursive_directory_iterator*<br/>
[Recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md)にコピーされる、`recursive_directory_iterator`します。

## <a name="op_eq"></a> recursive_directory_iterator::operator==

返します**true**両方の場合にのみ`*this`と*右*シーケンス末尾の反復子またはその両方がないエンド-の-シーケンスの反復子。

```cpp
bool operator==(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>パラメーター

*right*<br/>
[Recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md)比較します。

## <a name="op_multiply"></a> recursive_directory_iterator::operator *

`myentry` を返します。

```cpp
const directory_entry& operator*() const;
```

## <a name="op_cast"></a> recursive_directory_iterator::operator->

`&**this` を返します。

```cpp
const directory_entry * operator->() const;
```

## <a name="op_increment"></a> recursive_directory_iterator::operator++

インクリメント、`recursive_directory_iterator`します。

```cpp
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```

### <a name="parameters"></a>パラメーター

*int*<br/>
指定された増分値。

### <a name="remarks"></a>Remarks

最初のメンバー関数の呼び出し`increment()`、戻ります`*this`します。 2 番目のメンバー関数の呼び出し、オブジェクトのコピー`increment()`コピーを返します。

## <a name="options"></a> recursive_directory_iterator::options

`myoptions` を返します。

```cpp
directory_options options() const;
```

## <a name="pop"></a> recursive_directory_iterator::pop

次のオブジェクトを返します。

```cpp
void pop();
```

### <a name="remarks"></a>Remarks

場合`depth() == 0`シーケンス末尾の反復子になります。 そうでない場合、メンバー関数は現在の (最も深い) ディレクトリのスキャンを中断し、1 つ下の深さから再開します。

## <a name="recursion_pending"></a> recursive_directory_iterator::recursion_pending

`!no_push` を返します。

```cpp
bool recursion_pending() const;
```

## <a name="recursive_directory_iterator"></a> recursive_directory_iterator::recursive_directory_iterator

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

*pval*<br/>
指定するパス。

*error_code*<br/>
指定したエラー コード。

*opts*<br/>
指定したディレクトリのオプション。

*recursive_directory_iterator*<br/>
構築された `recursive_directory_iterator` のコピー元となる `recursive_directory_iterator`。

### <a name="remarks"></a>Remarks

1 つ目のコンストラクターは、end-of-sequence 反復子を生成します。 2 番目と 3 番目のコンス トラクター ストア**false**で`no_push`と`directory_options::none`で`myoptions`、開いて読み取ろうと試みます*pval*ディレクトリとして。 初期化が成功すると、`mystack`と`myentry`; 入れ子になったシーケンス内の最初のディレクトリでないファイル名を指定するシーケンスの末尾の反復子を生成します。

4 番目と 5 番目のコンス トラクターと動作、2 番目と 3 つ目として格納している点を除いて*opts*で`myoptions`します。 既定のコンストラクターは想定どおりの動作をします。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)<br/>
