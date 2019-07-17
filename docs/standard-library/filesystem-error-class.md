---
title: filesystem_error クラス
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::filesystem_error
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
ms.openlocfilehash: c3dbfc080f0a1494950016f42189d932be05b0f1
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240740"
---
# <a name="filesystemerror-class"></a>filesystem_error クラス

低レベル システム オーバーフローをレポートするためにスローされるすべての例外のための基底クラス。

## <a name="syntax"></a>構文

```cpp
class filesystem_error    : public system_error;
```

## <a name="remarks"></a>Remarks

このクラスは、\<filesystem> 関数のエラーを報告するためにスローされる例外すべてに対する基底クラスとして機能します。 型のオブジェクトを格納します`string`という`mymesg`説明の目的でここをクリックします。 型の 2 つのオブジェクトも格納`path`という`mypval1`と`mypval2`します。

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|||
|-|-|
|[filesystem_error](#filesystem_error)|構築、`filesystem_error`メッセージ。|

### <a name="functions"></a>関数

|||
|-|-|
|[path1](#path1)|`mypval1` を返します。|
|[path2](#path2)|`mypval2` を返します。|
|[どのような](#what)|`NTBS` へのポインターを返します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<filesystem >

**名前空間:** std::experimental::filesystem

## <a name="filesystem_error"></a> filesystem_error

最初のコンス トラクターからメッセージを構築する*what_arg*と*ec*します。 2 番目のコンス トラクターもからメッセージを構築*pval1*に格納している`mypval1`します。 3 番目のコンス トラクターもからメッセージを構築*pval1*に格納している`mypval1`との間*pval2*に格納している`mypval2`します。

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
指定したメッセージ。

*ec*\
エラー コードを指定します。

*mypval1*\
さらに指定したメッセージのパラメーター。

*mypval2*\
さらに指定したメッセージのパラメーター。

## <a name="path1"></a> path1

このメンバー関数は、`mypval1` を返します。

```cpp
const path& path1() const noexcept;
```

## <a name="path2"></a> path2

このメンバー関数は、`mypval2` を返します。

```cpp
const path& path2() const noexcept;
```

## <a name="what"></a> どのような

このメンバー関数へのポインターを返します、`NTBS`から構成可能であれば、 `runtime_error::what()`、 `system_error::what()`、 `mymesg`、 `mypval1.native_string()`、および`mypval2.native_string()`します。

```cpp
const char *what() const noexcept;
```
