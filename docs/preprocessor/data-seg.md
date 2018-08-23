---
title: data_seg |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- data_seg_CPP
- vc-pragma.data_seg
dev_langs:
- C++
helpviewer_keywords:
- data_seg pragma
- pragmas, data_seg
ms.assetid: 65c66466-4c98-494f-93af-106beb4caf78
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b1be97919f0f5b55d6e63eca8e59eb15e8ef9dff
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2018
ms.locfileid: "42541001"
---
# <a name="dataseg"></a>data_seg
初期化された変数が格納される、.obj ファイルのデータ セグメントを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma data_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Remarks 

用語の意味*セグメント*と*セクション*はこのトピックでは互換性があります。  
  
OBJ ファイルを表示できる、 [dumpbin](../build/reference/dumpbin-command-line.md)アプリケーション。 初期化される変数の .obj ファイルの既定セグメントは、.data です。 初期化されていない変数は、ゼロに初期化されたものと見なされ、bss に格納されます。  
  
**data_seg**パラメーターなしで、セグメントを .data にリセットします。  
  
*プッシュ*(省略可能)  
レコードを内部コンパイラ スタックに格納します。 A*プッシュ*できますが、*識別子*と*セグメント名*します。  
  
*pop* (省略可能)  
内部コンパイラ スタックの最上部からレコードを削除します。  
  
*識別子*(省略可能)  
使用すると*プッシュ*、内部コンパイラ スタックのレコードに名前を割り当てます。 使用すると*pop*、レコードまで内部スタックからポップ*識別子*が削除された場合*識別子*は内部のスタックに何もポップされます。  
  
*識別子*により、複数のレコードを 1 つのポップを*pop*コマンド。  
  
*"segment-name"*(optional)  
引数の名前。 使用すると*pop*、スタックがポップされ、*セグメント名*がアクティブなセグメント名になります。  
  
*「セグメント クラス」* (省略可能)  
Version 2.0 未満の C++ との互換性のために残されています。 これは無視されます。  
  
## <a name="example"></a>例  
  
```cpp  
// pragma_directive_data_seg.cpp  
int h = 1;                     // stored in .data  
int i = 0;                     // stored in .bss  
#pragma data_seg(".my_data1")  
int j = 1;                     // stored in "my_data1"  
  
#pragma data_seg(push, stack1, ".my_data2")     
int l = 2;                     // stored in "my_data2"  
  
#pragma data_seg(pop, stack1)   // pop stack1 off the stack  
int m = 3;                     // stored in "stack_data1"  
  
int main() {  
}  
```  
  
使用して割り当てられたデータ**data_seg**その位置に関する情報を保持しません。  
  
参照してください[/section](../build/reference/section-specify-section-attributes.md)に対して一連の名前のセクションを作成するときに使用する必要があります。  
  
Const 変数のセクションを指定することもできます ([const_seg](../preprocessor/const-seg.md))、初期化されていないデータ ([bss_seg](../preprocessor/bss-seg.md))、および関数 ([code_seg](../preprocessor/code-seg.md))。  
  
## <a name="see-also"></a>関連項目  
 
[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)