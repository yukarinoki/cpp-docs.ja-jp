---
title: filesystem_error クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::filesystem_error
dev_langs:
- C++
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ec0a30a8ee193db362efa375f6e9d0f5746a56f
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105303"
---
# <a name="filesystemerror-class"></a>filesystem_error クラス

低レベル システム オーバーフローをレポートするためにスローされるすべての例外のための基底クラス。

## <a name="syntax"></a>構文

```cpp
class filesystem_error    : public system_error;
```

## <a name="remarks"></a>Remarks

このクラスは、\<filesystem> 関数のエラーを報告するためにスローされる例外すべてに対する基底クラスとして機能します。 型のオブジェクトを格納します`string`という`mymesg`説明の目的でここをクリックします。 型の 2 つのオブジェクトも格納`path`という`mypval1`と`mypval2`します。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[filesystem_error](#filesystem_error)|構築、`filesystem_error`メッセージ。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[path1](#path1)|`mypval1` を返します。|
|[path2](#path2)|`mypval2` を返します。|
|[どのような](#what)|`NTBS` へのポインターを返します。|

## <a name="requirements"></a>要件

**ヘッダー:** \<filesystem >

**名前空間:** std::experimental::filesystem

## <a name="filesystem_error"></a> filesystem_error::filesystem_error

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

*what_arg*<br/>
指定したメッセージ。

*ec*<br/>
エラー コードを指定します。

*mypval1*<br/>
さらに指定したメッセージのパラメーター。

*mypval2*<br/>
さらに指定したメッセージのパラメーター。

## <a name="path1"></a> filesystem_error::path1

このメンバー関数は、`mypval1` を返します。

```cpp
const path& path1() const noexcept;
```

## <a name="path2"></a> filesystem_error::path2

このメンバー関数は、`mypval2` を返します。

```cpp
const path& path2() const noexcept;
```

## <a name="what"></a> filesystem_error::what

このメンバー関数へのポインターを返します、`NTBS`から構成可能であれば、 `runtime_error::what()`、 `system_error::what()`、 `mymesg`、 `mypval1.native_string()`、および`mypval2.native_string()`します。

```cpp
const char *what() const noexcept;
```

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[system_error クラス](../standard-library/system-error-class.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[\<exception>](../standard-library/exception.md)<br/>
