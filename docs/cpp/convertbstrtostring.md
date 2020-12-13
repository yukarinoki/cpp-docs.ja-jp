---
description: 詳細については、「ConvertBSTRToString」を参照してください。
title: ConvertBSTRToString
ms.date: 11/04/2016
f1_keywords:
- ConvertBSTRToString
helpviewer_keywords:
- ConvertBSTRToString function
ms.assetid: ab6ce555-3d75-4e9c-9cb8-ada6d8ce43b1
ms.openlocfilehash: 72d6033003f186f358d9b4143498df65858ee354
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344615"
---
# <a name="convertbstrtostring"></a>ConvertBSTRToString

**Microsoft 固有の仕様**

`BSTR` 値を `char *` に変換します。

## <a name="syntax"></a>構文

```
char* __stdcall ConvertBSTRToString(BSTR pSrc);
```

#### <a name="parameters"></a>パラメーター

*.Psrc*<br/>
BSTR 変数。

## <a name="remarks"></a>解説

**Convertbstrtostring** は、削除する必要がある文字列を割り当てます。

## <a name="example"></a>例

```cpp
// ConvertBSTRToString.cpp
#include <comutil.h>
#include <stdio.h>

#pragma comment(lib, "comsuppw.lib")

int main() {
   BSTR bstrText = ::SysAllocString(L"Test");
   wprintf_s(L"BSTR text: %s\n", bstrText);

   char* lpszText2 = _com_util::ConvertBSTRToString(bstrText);
   printf_s("char * text: %s\n", lpszText2);

   SysFreeString(bstrText);
   delete[] lpszText2;
}
```

```Output
BSTR text: Test
char * text: Test
```

**Microsoft 固有の仕様はここまで**

## <a name="requirements"></a>要件

**ヘッダー:**\<comutil.h>

**Lib:** comsuppw または comsuppw (詳細について [は、「/zc: Wchar_t (wchar_t ネイティブ型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 」を参照してください)

## <a name="see-also"></a>関連項目

[コンパイラ COM グローバル関数](../cpp/compiler-com-global-functions.md)
