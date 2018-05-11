---
title: recursive_directory_iterator クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
dev_langs:
- C++
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd876ec21379d59445b88bdc08a1c7b831cb94fa
ms.sourcegitcommit: 96cdc2da0d8c3783cc2ce03bd280a5430e1ac01d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
---
# <a name="recursivedirectoryiterator-class"></a>recursive_directory_iterator クラス

ディレクトリ内のファイル名を走査する入力反復子を記述します。反復子は再帰的にサブディレクトリに下ることができます。 反復子 X の場合、式 *X の結果は、ファイル名とそのステータスに関する既知の情報をラップする directory_entry クラスのオブジェクトになります。

詳細およびコード例については、「[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)」を参照してください。

## <a name="syntax"></a>構文

```cpp
class recursive_directory_iterator;
```

## <a name="remarks"></a>コメント

テンプレート クラスは以下を格納します。

1. 走査するディレクトリのネストを表す stack<pair\<directory_iterator, path>> 型のオブジェクト。ここでは、このオブジェクトに mystack という名前を付けて説明を進めます。

1. ディレクトリ シーケンス内の現在のファイル名を表す directory_entry 型のオブジェクト。ここでは、myentry という名前を付けます。

1. 再帰的にサブディレクトリに下ることが無効になっているかどうかを記録する bool 型のオブジェクト。ここでは、no_push という名前を付けます。

1. 構築時に設定されたオプションを記録する directory_options 型のオブジェクト。ここでは、myoptions という名前を付けます。

既定で構築される recursive_directory_entry 型のオブジェクトは、mystack.top().first に end-of-sequence 反復子を持つため、シーケンスの終端を示す反復子を表します。たとえば、def (ディレクトリ)、def/ghi、および jkl というエントリを持つディレクトリ abc がある場合、次のコードは

```cpp
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)
    visit(next->path());
```

引数 `path("abc/def/ghi") and path("abc/jkl").`を使用して visit を呼び出します。次の 2 つの方法でディレクトリ サブツリーの走査の条件を指定できます。

1. 値が directory_options::follow_directory_symlink の directory_options 引数を使って recursive_directory_iterator を構築した場合にのみ、ディレクトリ symlink がスキャンされます。

1. disable_recursion_pending を呼び出した場合は、インクリメント中に検出された後続ディレクトリは再帰的にスキャンされません。

## <a name="recursivedirectoryiteratordepth"></a>recursive_directory_iterator::depth

```cpp
int depth() const;
```

mystack.size() - 1 を返すため、pval が深さ 0 になります。

## <a name="recursivedirectoryiteratordisablerecursionpending"></a>recursive_directory_iterator::disable_recursion_pending

```cpp
void disable_recursion_pending();
```

このメンバー関数は、no_push に true を格納します。

## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator!=

```cpp
bool operator!=(const recursive_directory_iterator& right) const;
```

このメンバー演算子は、!(*this == right) を返します。

## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator=

```cpp
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;
```

この既定のメンバー代入演算子は想定どおりに動作します。

## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator==

```cpp
bool operator==(const recursive_directory_iterator& right) const;
```

このメンバー演算子は、*this と right の両方が end-of-sequence 反復子の場合または両方が end-of-sequence 反復子でない場合にのみ、true を返します。

## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator*

```cpp
const directory_entry& operator*() const;
```

このメンバー演算子は、myentry を返します。

## <a name="recursivedirectoryiteratoroperator-"></a>recursive_directory_iterator::operator->

```cpp
const directory_entry * operator->() const;
```

&**this を返します。

## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator++

```cpp
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```

1 つ目のメンバー関数は、increment() を呼び出してから、*this を返します。 2 つ目のメンバー関数は、オブジェクトのコピーを作成して、increment() を呼び出してから、そのコピーを返します。

## <a name="recursivedirectoryiteratoroptions"></a>recursive_directory_iterator::options

```cpp
directory_options options() const;
```

myoptions を返します。

## <a name="recursivedirectoryiteratorpop"></a>recursive_directory_iterator::pop

```cpp
void pop();
```

depth() == 0 の場合は、オブジェクトが end-of-sequence 反復子になります。 そうでない場合、メンバー関数は現在の (最も深い) ディレクトリのスキャンを中断し、1 つ下の深さから再開します。

## <a name="recursivedirectoryiteratorrecursionpending"></a>recursive_directory_iterator::recursion_pending

```cpp
bool recursion_pending() const;
```

!no_push を返します。

## <a name="recursivedirectoryiteratorrecursivedirectoryiterator"></a>recursive_directory_iterator::recursive_directory_iterator

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

1 つ目のコンストラクターは、end-of-sequence 反復子を生成します。 2 つ目と 3 つ目のコンストラクターは、no_push に false を、myoptions に directory_options::none を格納してから、pval をディレクトリとして開いて読み取ろうとします。 成功した場合は、ネストされたシーケンスに含まれる、ディレクトリでない 1 つ目のファイル名を指すように mystack と myentry を初期化します。成功しなかった場合は、end-of-sequence 反復子を生成します。

4 つ目と 5 つ目のコンストラクターは、最初に myoptions に opts を格納することを除いて、2 つ目と 3 つ目のコンストラクターと同じ動作をします。 既定のコンストラクターは想定どおりの動作をします。

## <a name="recursivedirectoryiteratorincrement"></a>recursive_directory_iterator::increment

```cpp
recursive_directory_iterator& increment(error_code& ec) noexcept;
```

この関数は、ネストされたシーケンス内の次のファイル名に進もうとします。 成功した場合は、myentry にそのファイル名を格納します。成功しなかった場合は、end-of-sequence 反復子を生成します。

## <a name="requirements"></a>要件

**ヘッダー:** \<filesystem >

**名前空間:** std::tr2::sys

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)<br/>
