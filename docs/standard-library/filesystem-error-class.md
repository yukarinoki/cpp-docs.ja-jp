---
title: filesystem_error クラス
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::filesystem_error
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
ms.openlocfilehash: 1d142057859f1ca173f8953b34c07bbb3803ecba
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835871"
---
# <a name="filesystem_error-class"></a>filesystem_error クラス

低レベル システム オーバーフローをレポートするためにスローされるすべての例外のための基底クラス。

## <a name="syntax"></a>構文

```cpp
class filesystem_error    : public system_error;
```

## <a name="remarks"></a>解説

クラスは、関数のエラーを報告するためにスローされるすべての例外の基底クラスとして機能し \<filesystem> ます。 このメソッドは、型のオブジェクトを格納します。これは、 `string` `mymesg` exposition の目的でここで呼び出されます。 また `path` 、とと呼ばれる型の2つのオブジェクトも格納し `mypval1` `mypval2` ます。

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|名前|説明|
|-|-|
|[filesystem_error](#filesystem_error)|メッセージを構築 `filesystem_error` します。|

### <a name="functions"></a>Functions

|名前|説明|
|-|-|
|[path1](#path1)|`mypval1` を返します。|
|[path2](#path2)|`mypval2` を返します。|
|[結果](#what)|`NTBS` へのポインターを返します。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<filesystem>

**名前空間:** std::experimental::filesystem

## <a name="filesystem_error"></a><a name="filesystem_error"></a> filesystem_error

最初のコンストラクターは *what_arg* および *ec*からメッセージを構築します。 2番目のコンストラクターは、 *pval1*からメッセージを構築します。このメッセージはに格納さ `mypval1` れます。 また、3番目のコンストラクターは、 *pval1*からメッセージを構築します。このメッセージは、に格納さ `mypval1` れ、 *pval2*から格納さ `mypval2` れます。

```cpp
filesystem_error(const string& what_arg,
    error_code ec);

filesystem_error(const string& what_arg,
    const path& pval1,
    error_code ec);

filesystem_error(const string& what_arg,
    const path& pval1,
    const path& pval2,
    error_code ec);
```

### <a name="parameters"></a>パラメーター

*what_arg*\
指定されたメッセージ。

*c*\
指定されたエラーコードです。

*mypval1*\
さらに指定されたメッセージパラメーター。

*mypval2*\
さらに指定されたメッセージパラメーター。

## <a name="path1"></a><a name="path1"></a> path1

このメンバー関数は、`mypval1` を返します。

```cpp
const path& path1() const noexcept;
```

## <a name="path2"></a><a name="path2"></a> path2

このメンバー関数は、`mypval2` を返します。

```cpp
const path& path2() const noexcept;
```

## <a name="what"></a><a name="what"></a> 結果

このメンバー関数は、(可能であれば、、、、、およびから構成される) へのポインターを返し `NTBS` `runtime_error::what()` `system_error::what()` `mymesg` `mypval1.native_string()` `mypval2.native_string()` ます。

```cpp
const char *what() const noexcept;
```
