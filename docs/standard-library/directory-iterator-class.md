---
title: directory_iterator クラス
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::directory_iterator
- filesystem/std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::increment
- filesystem/std::experimental::filesystem::directory_iterator::operator=
- filesystem/std::experimental::filesystem::directory_iterator::operator==
- filesystem/std::experimental::filesystem::directory_iterator::operator!=
- filesystem/std::experimental::filesystem::directory_iterator::operator*
- filesystem/std::experimental::filesystem::directory_iterator::operator-&gt;
- filesystem/std::experimental::filesystem::directory_iterator::operator++
ms.assetid: dca2ecf8-3e69-4644-a83d-705061e10cc8
helpviewer_keywords:
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::directory_iterator::directory_iterator
- std::experimental::filesystem::directory_iterator::increment
- std::experimental::filesystem::directory_iterator::operator=
- std::experimental::filesystem::directory_iterator::operator==
- std::experimental::filesystem::directory_iterator::operator!=
- std::experimental::filesystem::directory_iterator::operator*
- std::experimental::filesystem::directory_iterator::operator-&gt;
- std::experimental::filesystem::directory_iterator::operator++
ms.openlocfilehash: a7ccc2a941da079e14092af5b81dc537db4a48c0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215778"
---
# <a name="directory_iterator-class"></a>directory_iterator クラス

ディレクトリのファイル名を走査する入力反復子を表します。 反復子の場合 `X` 、式は、 `*X` `directory_entry` ファイル名をラップするクラスのオブジェクトと、その状態に関する既知のものに評価されます。

クラスは、型のオブジェクトを格納します。このオブジェクトは、 `path` `mydir` シーケンス対象のディレクトリの名前を表す exposition の目的で、ここでは、 `directory_entry` `myentry` ディレクトリシーケンス内の現在のファイル名を表す型のオブジェクトを表します。 型の既定の構築オブジェクトは、 `directory_entry` 空のパス名を持ち、 `mydir` シーケンスの末尾の反復子を表します。

たとえば、 `abc` とというエントリを持つディレクトリには、次のコードを指定し `def` `ghi` ます。

`for (directory_iterator next(path("abc")), end; next != end; ++next)     visit(next->path());`

は、引数とを指定してを呼び出し `visit` `path("abc/def")` `path("abc/ghi")` ます。

詳細とコード例については、「[ファイルシステムのナビゲーション (C++)](../standard-library/file-system-navigation.md)」を参照してください。

## <a name="syntax"></a>構文

```cpp
class directory_iterator;
```

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[directory_iterator](#directory_iterator)|ディレクトリ内のファイル名をシーケンス処理する入力反復子を構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[increment](#increment)|ディレクトリ内の次のファイル名への進みを試みます。|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[operator! =](#op_neq)|`!(*this == right)` を返します。|
|[operator =](#op_as)|この既定のメンバー代入演算子は想定どおりに動作します。|
|[operator = =](#op_eq)|**`true`** との両方 **`*this`** がシーケンス*right*末尾の反復子であるか、両方がシーケンスの末尾の反復子でない場合にのみ、を返します。|
|[operator](#op_star)|`myentry` を返します。|
|[演算子->](#op_cast)|`&**this` を返します。|
|[+ + 演算子](#op_increment)|`increment()`を呼び出し、を返すか、 **`*this`** またはオブジェクトのコピーを作成してを呼び出し `increment()` 、そのコピーを返します。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<experimental/filesystem>

**名前空間:** std::experimental::filesystem

## <a name="directory_iteratordirectory_iterator"></a><a name="directory_iterator"></a>directory_iterator::d irectory_iterator

1 つ目のコンストラクターは、end-of-sequence 反復子を生成します。 2番目と3番目のコンストラクターは、 *pval*をに格納し、を `mydir` 開いて `mydir` ディレクトリとして読み取ります。 成功した場合は、のディレクトリにある最初のファイル名を格納します。それ以外の場合は、 `myentry` シーケンス末尾の反復子を生成します。

既定のコンストラクターは想定どおりの動作をします。

```cpp
directory_iterator() noexcept;
explicit directory_iterator(const path& pval);

directory_iterator(const path& pval, error_code& ec) noexcept;
directory_iterator(const directory_iterator&) = default;
directory_iterator(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>パラメーター

*pval*\
格納されているファイル名のパス。

*c*\
ステータスエラーコード。

*directory_iterator*\
格納されているオブジェクト。

## <a name="directory_iteratorincrement"></a><a name="increment"></a>directory_iterator:: increment

この関数は、ディレクトリ内の次のファイル名に進もうとします。 成功した場合は、そのファイル名をに格納します。それ以外の場合は、 `myentry` シーケンス末尾の反復子を生成します。

```cpp
directory_iterator& increment(error_code& ec) noexcept;
```

## <a name="directory_iteratoroperator"></a><a name="op_neq"></a>directory_iterator:: operator! =

このメンバー演算子は、 `!(*this == right)`を返します。

```cpp
bool operator!=(const directory_iterator& right) const;
```

### <a name="parameters"></a>パラメーター

*そうです*\
と比較する[directory_iterator](../standard-library/directory-iterator-class.md) `directory_iterator` 。

## <a name="directory_iteratoroperator"></a><a name="op_as"></a>directory_iterator:: operator =

この既定のメンバー代入演算子は想定どおりに動作します。

```cpp
directory_iterator& operator=(const directory_iterator&) = default;
directory_iterator& operator=(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>パラメーター

*そうです*\
にコピーされる[directory_iterator](../standard-library/directory-iterator-class.md) `directory_iterator` 。

## <a name="directory_iteratoroperator"></a><a name="op_eq"></a>directory_iterator:: operator = =

メンバー演算子は、 **`true`** との両方 **`*this`** が*right*シーケンス末尾の反復子であるか、両方がシーケンスの末尾の反復子でない場合にのみ、を返します。

```cpp
bool operator==(const directory_iterator& right) const;
```

### <a name="parameters"></a>パラメーター

*そうです*\
と比較する[directory_iterator](../standard-library/directory-iterator-class.md) `directory_iterator` 。

## <a name="directory_iteratoroperator"></a><a name="op_star"></a>directory_iterator:: operator *

このメンバー演算子は、 `myentry`を返します。

```cpp
const directory_entry& operator*() const;
```

## <a name="directory_iteratoroperator-"></a><a name="op_cast"></a>directory_iterator:: operator->

このメンバー関数は、`&**this` を返します。

```cpp
const directory_entry * operator->() const;
```

## <a name="directory_iteratoroperator"></a><a name="op_increment"></a>directory_iterator:: operator + +

最初のメンバー関数は `increment()` を呼び出し、を返し **`*this`** ます。 2番目のメンバー関数は、オブジェクトのコピーを作成して `increment()` を呼び出し、そのコピーを返します。

```cpp
directory_iterator& operator++();
directory_iterator& operator++(int);
```

### <a name="parameters"></a>パラメーター

*通り*\
インクリメントの数。

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem>](../standard-library/filesystem.md)\
[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)
