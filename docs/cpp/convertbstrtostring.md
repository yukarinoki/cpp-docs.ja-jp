---
title: ConvertBSTRToString |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- ConvertBSTRToString
dev_langs:
- C++
helpviewer_keywords:
- ConvertBSTRToString function
ms.assetid: ab6ce555-3d75-4e9c-9cb8-ada6d8ce43b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db1f512b10bdedffa5b6978b735c881dc21370ce
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406703"
---
# <a name="convertbstrtostring"></a>ConvertBSTRToString
**Microsoft 固有の仕様**  
  
 変換を`BSTR`値を`char *`します。  
  
## <a name="syntax"></a>構文  
  
```  
char* __stdcall ConvertBSTRToString(BSTR pSrc);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *pSrc*  
 BSTR 変数。  
  
## <a name="remarks"></a>Remarks  
 **ConvertBSTRToString**する必要がありますを削除する文字列を割り当てます。  
  
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
 **ヘッダー:** \<comutil.h >。  
  
 **Lib:** comsuppw.lib または comsuppwd.lib (を参照してください[/Zc:wchar_t (wchar_t をネイティブ型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)詳細)  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ COM のグローバル関数](../cpp/compiler-com-global-functions.md)