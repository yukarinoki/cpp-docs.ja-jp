---
title: regex_error クラス
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_error
- regex/std::regex_error::code
helpviewer_keywords:
- regex_error class
ms.assetid: 3333a1a3-ca6f-4612-84b2-1b4c7e3db5a4
ms.openlocfilehash: f8f3c88c1b203ed7fcea148843fa99590e27b888
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331866"
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

|Constructor|説明|
|-|-|
|[regex_error](#regex_error)|オブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[code](#code)|エラー コードを返します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<regex>

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

## <a name="regex_errorcode"></a><a name="code"></a>regex_error::コード

エラー コードを返します。

```cpp
regex_constants::error_code code() const;
```

### <a name="remarks"></a>解説

このメンバー関数は、オブジェクトのコンストラクターに渡された値を返します。

## <a name="regex_errorregex_error"></a><a name="regex_error"></a>regex_error::regex_error

オブジェクトを構築します。

```cpp
regex_error(regex_constants::error_code error);
```

### <a name="parameters"></a>パラメーター

*エラー*\
エラー コード。

### <a name="remarks"></a>解説

このコンストラクターは、値*error*を保持するオブジェクトを構築します。

## <a name="see-also"></a>関連項目

[\<正規表現>](../standard-library/regex.md)\
[regex_constantsクラス](../standard-library/regex-constants-class.md)\
[\<正規表現>関数](../standard-library/regex-functions.md)\
[regex_iteratorクラス](../standard-library/regex-iterator-class.md)\
[\<正規表現>演算子](../standard-library/regex-operators.md)\
[regex_token_iteratorクラス](../standard-library/regex-token-iterator-class.md)\
[regex_traitsクラス](../standard-library/regex-traits-class.md)\
[\<正規表現>のタイプ定義](../standard-library/regex-typedefs.md)
