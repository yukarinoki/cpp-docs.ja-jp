---
title: マネージ、アンマネージ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.unmanaged
- managed_CPP
- unmanaged_CPP
- vc-pragma.managed
dev_langs:
- C++
helpviewer_keywords:
- managed pragma
- pragmas, unmanaged
- pragmas, managed
- unmanaged pragma
ms.assetid: f072ddcc-e1ec-408a-8ce1-326ddb60e4a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 316866ac047b607ec4c92d7c6d4f8ff233ed9a3f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33846377"
---
# <a name="managed-unmanaged"></a>マネージ、アンマネージ
関数をマネージまたはアンマネージとしてコンパイルするために関数レベルの制御を有効にします。  
  
## <a name="syntax"></a>構文  
  
```  
  
      #pragma managed  
#pragma unmanaged  
#pragma managed([push,] on | off)  
#pragma managed(pop)  
```  
  
## <a name="remarks"></a>コメント  
 [/Clr](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションは、モジュール レベルの制御関数をマネージまたはアンマネージとしてコンパイルします。  
  
 アンマネージ関数は、ネイティブ プラットフォーム用にコンパイルされ、プログラムのその部分の実行は、共通言語ランタイムによってネイティブ プラットフォームに渡されます。  
  
 既定では管理対象として、関数がコンパイルされたときに **/clr**を使用します。  
  
 これらのプラグマを適用するときは次のようにします。  
  
-   関数の前にあり関数本体内にはないプラグマを追加します。  
  
-   `#include` ステートメントの後にプラグマを追加します。 `#include` ステートメントの前でこれらのプラグマを使用しないでください。  
  
 コンパイラは無視、`managed`と`unmanaged`プラグマ場合 **/clr**コンパイルでは使用されません。  
  
 テンプレート関数がインスタンス化されるとき、テンプレートの定義時のプラグマの状態により、マネージかアンマネージかが決まります。  
  
 詳細については、次を参照してください。[混在アセンブリの初期化](../dotnet/initialization-of-mixed-assemblies.md)です。  
  
## <a name="example"></a>例  
  
```cpp  
// pragma_directives_managed_unmanaged.cpp  
// compile with: /clr  
#include <stdio.h>  
  
// func1 is managed  
void func1() {  
   System::Console::WriteLine("In managed function.");  
}  
  
// #pragma unmanaged  
// push managed state on to stack and set unmanaged state  
#pragma managed(push, off)  
  
// func2 is unmanaged  
void func2() {  
   printf("In unmanaged function.\n");  
}  
  
// #pragma managed  
#pragma managed(pop)  
  
// main is managed  
int main() {  
   func1();  
   func2();  
}  
```  
  
```Output  
In managed function.  
In unmanaged function.  
```  
  
## <a name="see-also"></a>関連項目  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)