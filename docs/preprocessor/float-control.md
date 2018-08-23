---
title: float_control |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
dev_langs:
- C++
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b9b94e5b8eccdc63735c7cb25faa7eacb1e23670
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2018
ms.locfileid: "42545782"
---
# <a name="floatcontrol"></a>float_control
関数の浮動小数点動作を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
float_control( value,setting [push] | push | pop )  
```  
  
## <a name="flags"></a>フラグ  
 
*値*、*設定* *[プッシュ]*  
浮動小数点の動作を指定します。 *値*できる`precise`または`except`します。 詳細については、「[/fp (浮動小数点の動作の指定)](../build/reference/fp-specify-floating-point-behavior.md)」を参照してください。 *設定*できます`on`または`off`します。  
  
場合*値*は`precise`、設定`precise`と`except`が指定されています。 `except` 設定することができますのみ`on`とき`precise`にも設定されている`on`。  
  
場合、省略可能な*プッシュ*トークンは追加、現在の設定*値*内部コンパイラ スタックにプッシュされます。  
  
*push*  
現在のプッシュ**float_control**内部コンパイラ スタックに設定  
  
*pop*  
削除、 **float_control**内部コンパイラ スタックの一番上から設定し、それは新しい**float_control**設定。  
  
## <a name="remarks"></a>Remarks  
 
`float_control precise` がオンの場合は、`except` をオフにすることはできません。 同様に、`precise` がオンになっている場合は、`fenv_access` をオフにすることはできません。 厳格なモデルから使用してモデルを高速にする、 **float_control**プラグマを使用して、次のコード。  
  
```  
#pragma float_control(except, off)  
#pragma fenv_access(off)  
#pragma float_control(precise, off)  
```  
  
高速モデルから厳格なモデルに移行する、 **float_control**プラグマを使用して、次のコード。  
  
```  
#pragma float_control(precise, on)  
#pragma fenv_access(on)  
#pragma float_control(except, on)  
```  
  
その他の浮動小数点プラグマには以下があります。  
  
- [fenv_access](../preprocessor/fenv-access.md)  
  
- [fp_contract](../preprocessor/fp-contract.md)  
  
## <a name="example"></a>例  
 
次の例は、プラグマを使用してオーバーフロー浮動小数点例外をキャッチする方法を示しています。 **float_control**します。  
  
```cpp  
// pragma_directive_float_control.cpp  
// compile with: /EHa  
#include <stdio.h>  
#include <float.h>  
  
double func( ) {  
   return 1.1e75;  
}  
  
#pragma float_control (except,on)  
  
int main( ) {  
   float u[1];  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, ~_EM_OVERFLOW, _MCW_EM);  
   if (err != 0)  
      printf_s("_controlfp_s failed!\n");  
  
   try  {  
      u[0] = func();  
      printf_s ("Fail");     
      return(1);  
   }   
  
   catch (...)  {  
      printf_s ("Pass");  
      return(0);  
   }  
}  
```  
  
```Output  
Pass  
```  
  
## <a name="see-also"></a>関連項目  
 
[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)  
