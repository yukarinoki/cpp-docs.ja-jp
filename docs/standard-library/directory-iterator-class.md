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
ms.openlocfilehash: 6763f2a96b771fadbec311cf8740352fff53e29a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413847"
---
# <a name="directoryiterator-class"></a>directory_iterator クラス

ディレクトリのファイル名を走査する入力反復子を表します。 反復子のため`X`、式`*X`クラスのオブジェクトを指す`directory_entry`ファイル名とその状態に関する既知の情報をラップします。

クラス型のオブジェクトを格納する`path`という`mydir`をシーケンス処理するディレクトリの名前を表す、説明のため、型のオブジェクトの`directory_entry`と呼ばれる`myentry`ここでは、現在を表しますディレクトリ シーケンス内のファイル名。 型の既定で構築されるオブジェクト`directory_entry`が空`mydir`パス名をシーケンス末尾の反復子を表します。

たとえば、ディレクトリを指定`abc`エントリを含む`def`と`ghi`コード。

`for (directory_iterator next(path("abc")), end; next != end; ++next)     visit(next->path());`

呼び出す`visit`引数`path("abc/def")`と`path("abc/ghi")`します。

詳細およびコード例については、「[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)」を参照してください。

## <a name="syntax"></a>構文

```cpp
class directory_iterator;
```

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[directory_iterator](#directory_iterator)|ディレクトリにファイル名を走査する入力反復子を構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[increment](#increment)|ディレクトリで次のファイル名に進もうとします。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator!=](#op_neq)|`!(*this == right)` を返します。|
|[operator=](#op_as)|この既定のメンバー代入演算子は想定どおりに動作します。|
|[operator==](#op_eq)|返します**true**両方の場合にのみ`*this`と*右*シーケンス末尾の反復子またはその両方がないエンド-の-シーケンスの反復子。|
|[operator*](#op_star)|`myentry` を返します。|
|[operator->](#op_cast)|`&**this` を返します。|
|[operator++](#op_increment)|呼び出し`increment()`、戻ります`*this`を呼び出し、オブジェクトのコピーを作成または`increment()`コピーを返します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<experimental/filesystem>

**名前空間:** std::experimental::filesystem

## <a name="directory_iterator"></a> directory_iterator::directory_iterator

1 つ目のコンストラクターは、end-of-sequence 反復子を生成します。 2 番目と 3 番目のコンス トラクター ストア*pval*で`mydir`、開いて読み取ろうと試みます`mydir`ディレクトリとして。 かどうかは成功すると、これら最初のファイル名をディレクトリに格納で`myentry`; シーケンス末尾の反復子を生成します。

既定のコンストラクターは想定どおりの動作をします。

```cpp
directory_iterator() noexcept;
explicit directory_iterator(const path& pval);

directory_iterator(const path& pval, error_code& ec) noexcept;
directory_iterator(const directory_iterator&) = default;
directory_iterator(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>パラメーター

*pval*<br/>
格納されているファイル名のパス。

*ec*<br/>
状態エラー コード。

*directory_iterator*<br/>
格納されているオブジェクト。

## <a name="increment"></a> directory_iterator::increment

この関数は、ディレクトリ内の次のファイル名に進もうとします。 かどうかは成功すると、そのファイル名を格納で`myentry`。 それ以外の場合、シーケンス末尾の反復子が生成されます。

```cpp
directory_iterator& increment(error_code& ec) noexcept;
```

## <a name="op_neq"></a> directory_iterator::operator! =

このメンバー演算子は、 `!(*this == right)`を返します。

```cpp
bool operator!=(const directory_iterator& right) const;
```

### <a name="parameters"></a>パラメーター

*right*<br/>
[Directory_iterator](../standard-library/directory-iterator-class.md)と比較される、`directory_iterator`します。

## <a name="op_as"></a> directory_iterator::operator =

この既定のメンバー代入演算子は想定どおりに動作します。

```cpp
directory_iterator& operator=(const directory_iterator&) = default;
directory_iterator& operator=(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>パラメーター

*right*<br/>
[Directory_iterator](../standard-library/directory-iterator-class.md)にコピーされる、`directory_iterator`します。

## <a name="op_eq"></a> directory_iterator::operator==

メンバー演算子を返します**true**両方の場合にのみ`*this`と*右*シーケンス末尾の反復子またはその両方がないエンド-の-シーケンスの反復子。

```cpp
bool operator==(const directory_iterator& right) const;
```

### <a name="parameters"></a>パラメーター

*right*<br/>
[Directory_iterator](../standard-library/directory-iterator-class.md)と比較される、`directory_iterator`します。

## <a name="op_star"></a> directory_iterator::operator*

このメンバー演算子は、 `myentry`を返します。

```cpp
const directory_entry& operator*() const;
```

## <a name="op_cast"></a> directory_iterator::operator->

このメンバー関数は、`&**this` を返します。

```cpp
const directory_entry * operator->() const;
```

## <a name="op_increment"></a> directory_iterator::operator++

最初のメンバー関数の呼び出し`increment()`、戻ります`*this`します。 2 番目のメンバー関数の呼び出し、オブジェクトのコピー`increment()`コピーを返します。

```cpp
directory_iterator& operator++();
directory_iterator& operator++(int);
```

### <a name="parameters"></a>パラメーター

*int*<br/>
インクリメントの数。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)<br/>
