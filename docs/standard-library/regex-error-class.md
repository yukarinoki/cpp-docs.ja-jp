---
description: '詳細情報: regex_error クラス'
title: regex_error クラス
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_error
- regex/std::regex_error::code
helpviewer_keywords:
- regex_error class
ms.assetid: 3333a1a3-ca6f-4612-84b2-1b4c7e3db5a4
ms.openlocfilehash: a6e2ace44c7463cbe43d000d3dabb9cf9f7d6676
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250505"
---
# <a name="regex_error-class"></a>regex_error クラス

正しくない basic_regex オブジェクトを報告します。

## <a name="syntax"></a>構文

```cpp
class regex_error
: public std::runtime_error
```

## <a name="remarks"></a>解説

このクラスは、 `basic_regex` オブジェクトの構築時または使用時に発生したエラーを報告するためにスローされる例外オブジェクトを表します。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[regex_error](#regex_error)|オブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[code](#code)|エラー コードを返します。|

## <a name="requirements"></a>要件

**ヘッダー:**\<regex>

**名前空間:** std

## <a name="example"></a>例

```cpp
// std__regex__regex_error.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
    {
    std::regex_error paren(std::regex_constants::error_paren);

    try
        {
        std::regex rx("(a");
        }
    catch (const std::regex_error& rerr)
        {
        std::cout << "regex error: "
            << (rerr.code() == paren.code() ? "unbalanced parentheses" : "")
            << std::endl;
        }
    catch (...)
        {
        std::cout << "unknown exception" << std::endl;
        }

    return (0);
    }
```

```Output
regex error: unbalanced parentheses
```

## <a name="regex_errorcode"></a><a name="code"></a> regex_error:: code

エラー コードを返します。

```cpp
regex_constants::error_code code() const;
```

### <a name="remarks"></a>解説

このメンバー関数は、オブジェクトのコンストラクターに渡された値を返します。

## <a name="regex_errorregex_error"></a><a name="regex_error"></a> regex_error:: regex_error

オブジェクトを構築します。

```cpp
regex_error(regex_constants::error_code error);
```

### <a name="parameters"></a>パラメーター

*エラー*\
エラー コード。

### <a name="remarks"></a>解説

コンストラクターは、値 *error* を保持するオブジェクトを構築します。

## <a name="see-also"></a>関連項目

[\<regex>](../standard-library/regex.md)\
[regex_constants クラス](../standard-library/regex-constants-class.md)\
[\<regex> 関数](../standard-library/regex-functions.md)\
[regex_iterator クラス](../standard-library/regex-iterator-class.md)\
[\<regex> 通信](../standard-library/regex-operators.md)\
[regex_token_iterator クラス](../standard-library/regex-token-iterator-class.md)\
[regex_traits クラス](../standard-library/regex-traits-class.md)\
[\<regex> typedef](../standard-library/regex-typedefs.md)
