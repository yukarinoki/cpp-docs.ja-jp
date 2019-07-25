---
title: recursive_directory_iterator クラス
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
ms.openlocfilehash: 98eaf2494a3bc17c0f9d11683fc67fed433ba3a5
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451702"
---
# <a name="recursivedirectoryiterator-class"></a>recursive_directory_iterator クラス

ディレクトリ内のファイル名をシーケンス処理する入力反復子を記述します。再帰的にサブディレクトリに向かって降順に並べ替えます。 反復子`X`の場合、式`*X`は、ファイル名をラップ`directory_entry`するクラスのオブジェクトと、その状態に関する既知のものに評価されます。

詳細およびコード例については、「[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)」を参照してください。

## <a name="syntax"></a>構文

```cpp
class recursive_directory_iterator;
```

## <a name="remarks"></a>Remarks

テンプレート クラスは以下を格納します。

1. シーケンスされるディレクトリ`stack<pair<directory_iterator, path>>`の入れ子`mystack`を表す、exposition の目的でここで呼び出される型のオブジェクト。

1. ここで呼び出さ`myentry`れる`directory_entry`型のオブジェクト。ディレクトリシーケンス内の現在のファイル名を表します。

1. ここで呼び出さ`no_push`れる**bool**型のオブジェクトは、サブディレクトリへの再帰降下が無効になっているかどうかを記録します。

1. ここで呼び出され`directory_options` `myoptions` 、構築時に確立されたオプションを記録する型のオブジェクト。

型`recursive_directory_entry`の既定の構築されたオブジェクトは、で`mystack.top().first`シーケンスの末尾の反復子を持ち、シーケンスの末尾の反復子を表します。 たとえば、ディレクトリ`abc`に`def/ghi`エントリ`def` (ディレクトリ)、、および`jkl`が指定されている場合、コードは次のようになります。

```cpp
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)
    visit(next->path());
```

は、引数`path("abc/def/ghi")`と`path("abc/jkl")`を使用して visit を呼び出します。 ディレクトリサブツリーの順序付けは、次の2つの方法で修飾できます。

1. ディレクトリシンボリックリンクは、値が`recursive_directory_iterator` `directory_options::follow_directory_symlink`である`directory_options`引数を使用してを構築する場合にのみスキャンされます。

1. を呼び出す`disable_recursion_pending`と、インクリメント中に発生した後続のディレクトリは再帰的にスキャンされません。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[recursive_directory_iterator](#recursive_directory_iterator)|`recursive_directory_iterator` を構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[デプス](#depth)|は`mystack.size() - 1`を返し`pval`ます。したがって、は深度0になります。|
|[disable_recursion_pending](#disable_recursion_pending)|に**true**を`no_push`格納します。|
|[increment](#increment)|は、次のファイル名に順に進みます。|
|[options](#options)|`myoptions` を返します。|
|[pop](#pop)|次のオブジェクトを返します。|
|[recursion_pending](#recursion_pending)|`!no_push` を返します。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator!=](#op_neq)|`!(*this == right)` を返します。|
|[operator=](#op_as)|この既定のメンバー代入演算子は想定どおりに動作します。|
|[operator==](#op_eq)|*との*両方`*this`がシーケンス末尾の反復子であるか、両方がシーケンスの末尾の反復子でない場合にのみ、 **true**を返します。|
|[operator*](#op_multiply)|`myentry` を返します。|
|[operator->](#op_cast)|`&**this` を返します。|
|[operator++](#op_increment)|を`recursive_directory_iterator`インクリメントします。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<ファイルシステム >

**名前空間:** std::tr2::sys

## <a name="depth"></a>recursive_directory_iterator::d epth

は`mystack.size() - 1`を返し`pval`ます。したがって、は深度0になります。

```cpp
int depth() const;
```

## <a name="disable_recursion_pending"></a>recursive_directory_iterator::d isable_recursion_pending

に**true**を`no_push`格納します。

```cpp
void disable_recursion_pending();
```

## <a name="increment"></a>recursive_directory_iterator:: increment

は、次のファイル名に順に進みます。

```cpp
recursive_directory_iterator& increment(error_code& ec) noexcept;
```

### <a name="parameters"></a>パラメーター

*c*\
指定されたエラーコードです。

### <a name="remarks"></a>Remarks

この関数は、ネストされたシーケンス内の次のファイル名に進もうとします。 成功した場合は、そのファイル`myentry`名をに格納します。それ以外の場合は、シーケンス末尾の反復子を生成します。

## <a name="op_neq"></a>recursive_directory_iterator:: operator! =

`!(*this == right)` を返します。

```cpp
bool operator!=(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>パラメーター

*そうです*\
比較対象の[recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) 。

## <a name="op_as"></a>recursive_directory_iterator:: operator =

この既定のメンバー代入演算子は想定どおりに動作します。

```cpp
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>パラメーター

*recursive_directory_iterator*\
に`recursive_directory_iterator`コピーされる[recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) 。

## <a name="op_eq"></a>recursive_directory_iterator:: operator = =

*との*両方`*this`がシーケンス末尾の反復子であるか、両方がシーケンスの末尾の反復子でない場合にのみ、 **true**を返します。

```cpp
bool operator==(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>パラメーター

*そうです*\
比較対象の[recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) 。

## <a name="op_multiply"></a>recursive_directory_iterator:: operator *

`myentry` を返します。

```cpp
const directory_entry& operator*() const;
```

## <a name="op_cast"></a>recursive_directory_iterator:: operator->

`&**this` を返します。

```cpp
const directory_entry * operator->() const;
```

## <a name="op_increment"></a>recursive_directory_iterator:: operator + +

を`recursive_directory_iterator`インクリメントします。

```cpp
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```

### <a name="parameters"></a>パラメーター

*通り*\
指定されたインクリメント。

### <a name="remarks"></a>Remarks

最初のメンバー関数は`increment()`を呼び出し、 `*this`を返します。 2番目のメンバー関数は、オブジェクトのコピーを`increment()`作成してを呼び出し、そのコピーを返します。

## <a name="options"></a>recursive_directory_iterator:: options

`myoptions` を返します。

```cpp
directory_options options() const;
```

## <a name="pop"></a>recursive_directory_iterator::p op

次のオブジェクトを返します。

```cpp
void pop();
```

### <a name="remarks"></a>Remarks

オブジェクト`depth() == 0`がシーケンス末尾の反復子になる場合は。 そうでない場合、メンバー関数は現在の (最も深い) ディレクトリのスキャンを中断し、1 つ下の深さから再開します。

## <a name="recursion_pending"></a>recursive_directory_iterator::recursion_pending

`!no_push` を返します。

```cpp
bool recursion_pending() const;
```

## <a name="recursive_directory_iterator"></a>recursive_directory_iterator::recursive_directory_iterator

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

### <a name="remarks"></a>Remarks

1 つ目のコンストラクターは、end-of-sequence 反復子を生成します。 2番目と3番目の`no_push`コンストラクター `directory_options::none`は`myoptions`、とに**false**を格納し、 *pval*をディレクトリとして開いて読み取ることを試みます。 成功した場合、 `mystack`入れ子`myentry`になったシーケンス内の最初の非ディレクトリファイル名を初期化して指定します。それ以外の場合は、シーケンス末尾の反復子を生成します。

4番目と5番目のコンストラクターは、最初に`myoptions`optin を格納する点を除いて、2番目と3番目のコンストラクターと同じように動作します。 既定のコンストラクターは想定どおりの動作をします。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem>](../standard-library/filesystem.md)\
[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)
