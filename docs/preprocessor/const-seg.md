---
title: const_seg |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.const_seg
- const_seg_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, const_seg
- const_seg pragma
ms.assetid: 1eb58ee2-fb0e-4a39-9621-699c8f5ef957
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3081837cc4516750f8c2c0d75cfc37eef208f9d
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2018
ms.locfileid: "42545785"
---
# <a name="constseg"></a>const_seg
セグメントを指定場所[const](../cpp/const-cpp.md)変数は、.obj ファイルに格納されます。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma const_seg ( [ [ { push | pop}, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Remarks  
 
用語の意味*セグメント*と*セクション*はこのトピックでは互換性があります。  
  
OBJ ファイルを表示できる、 [dumpbin](../build/reference/dumpbin-command-line.md)アプリケーション。 `const` 変数の .obj ファイルの既定セグメントは、.rdata です。 スカラーのような一部の `const` 変数は、コード ストリームに自動的にインライン展開されます。 インライン コードは、.rdata には現れません。  
  
`const_seg` 内に動的な初期化を必要とするオブジェクトを定義すると、未定義の動作が発生します。  
  
パラメーターなしの `#pragma const_seg` は、セグメントを .rdata にリセットします。  
  
*プッシュ*(省略可能)  
レコードを内部コンパイラ スタックに格納します。 A*プッシュ*できますが、*識別子*と*セグメント名*します。  
  
*pop* (省略可能)  
内部コンパイラ スタックの最上部からレコードを削除します。  
  
*識別子*(省略可能)  
使用すると*プッシュ*、内部コンパイラ スタックのレコードに名前を割り当てます。 使用すると*pop*、レコードまで内部スタックからポップ*識別子*が削除された場合*識別子*は内部のスタックに何もポップされます。  
  
使用して*識別子*により、複数のレコードを 1 つのポップを*pop*コマンド。  
  
"*セグメント名*"(省略可能)  
引数の名前。 使用すると*pop*、スタックがポップされ、*セグメント名*がアクティブなセグメント名になります。  
  
"*セグメント クラス*"(省略可能)  
Version 2.0 未満の C++ との互換性のために残されています。 これは無視されます。  
  
## <a name="example"></a>例  
  
```cpp  
// pragma_directive_const_seg.cpp  
// compile with: /EHsc  
#include <iostream>  
  
const int i = 7;               // inlined, not stored in .rdata  
const char sz1[]= "test1";     // stored in .rdata  
  
#pragma const_seg(".my_data1")  
const char sz2[]= "test2";     // stored in .my_data1  
  
#pragma const_seg(push, stack1, ".my_data2")  
const char sz3[]= "test3";     // stored in .my_data2  
  
#pragma const_seg(pop, stack1) // pop stack1 from stack  
const char sz4[]= "test4";     // stored in .my_data1  
  
int main() {  
    using namespace std;  
   // const data must be referenced to be put in .obj  
   cout << sz1 << endl;  
   cout << sz2 << endl;  
   cout << sz3 << endl;  
   cout << sz4 << endl;  
}  
```  
  
```Output  
test1  
test2  
test3  
test4  
```  
  
## <a name="comments"></a>コメント  
 
参照してください[/section](../build/reference/section-specify-section-attributes.md)に対して一連の名前のセクションを作成するときに使用する必要があります。  
  
初期化されたデータのセクションを指定することもできます ([data_seg](../preprocessor/data-seg.md))、初期化されていないデータ ([bss_seg](../preprocessor/bss-seg.md))、および関数 ([code_seg](../preprocessor/code-seg.md))。  
  
## <a name="see-also"></a>関連項目  
 
[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)