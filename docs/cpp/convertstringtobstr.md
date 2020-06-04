---
title: ConvertStringToBSTR
ms.date: 11/04/2016
f1_keywords:
- ConvertStringToBSTR
helpviewer_keywords:
- ConvertStringToBSTR function
ms.assetid: 071f9b3b-9643-4e06-a1e5-de96ed15bab2
ms.openlocfilehash: 2065011ee6bbf98ce2c83be494f1e6631af9f7cf
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170710"
---
# <a name="convertstringtobstr"></a>ConvertStringToBSTR

**Microsoft 固有の仕様**

`char *` 値を `BSTR` に変換します。

## <a name="syntax"></a>構文

```
BSTR __stdcall ConvertStringToBSTR(const char* pSrc)
```

#### <a name="parameters"></a>パラメーター

*.Psrc*<br/>
`char *` 変数です。

## <a name="example"></a>例

```cpp
// ConvertStringToBSTR.cpp
#include <comutil.h>
#include <stdio.h>

#pragma comment(lib, "comsuppw.lib")
#pragma comment(lib, "kernel32.lib")

int main() {
   char* lpszText = "Test";
   printf_s("char * text: %s\n", lpszText);

   BSTR bstrText = _com_util::ConvertStringToBSTR(lpszText);
   wprintf_s(L"BSTR text: %s\n", bstrText);

   SysFreeString(bstrText);
}
```

```Output
char * text: Test
BSTR text: Test
```

**Microsoft 固有の仕様はここまで**

## <a name="requirements"></a>必要条件

**ヘッダー:** \<comutil. h >

**Lib:** comsuppw または comsuppw (詳細について[は、「/zc: Wchar_t (wchar_t ネイティブ型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 」を参照してください)

## <a name="see-also"></a>参照

[コンパイラ COM のグローバル関数](../cpp/compiler-com-global-functions.md)
