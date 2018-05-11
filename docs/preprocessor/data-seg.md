---
title: data_seg |Microsoft ドキュメント
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
ms.openlocfilehash: 7a463d966c681557525bb9512762731c01a7ce30
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="dataseg"></a>data_seg
初期化された変数が格納される、.obj ファイルのデータ セグメントを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#pragma data_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>コメント  
 用語の意味*セグメント*と*セクション*はこのトピックでは互換性があります。  
  
 OBJ ファイルと見なすことができます、 [dumpbin](../build/reference/dumpbin-command-line.md)アプリケーションです。 初期化される変数の .obj ファイルの既定セグメントは、.data です。 初期化されていない変数は、ゼロに初期化されたものと見なされ、bss に格納されます。  
  
 **data_seg**パラメーターなしのセグメントを .data にリセットします。  
  
 **プッシュ**(省略可能)  
 レコードを内部コンパイラ スタックに格納します。 A**プッシュ**持つことができます、*識別子*と*セグメント名*です。  
  
 **pop** (省略可能)  
 内部コンパイラ スタックの最上部からレコードを削除します。  
  
 *識別子*(省略可能)  
 使用すると**プッシュ**、内部コンパイラ スタックのレコードに名前が割り当てられます。 使用すると**pop**、レコードまで内部スタックからポップ*識別子*が削除された場合は*識別子*がない内部スタックで、何もポップします。  
  
 *識別子*により、複数のレコードが 1 つでポップできます**pop**コマンド。  
  
 *"segment-name"*(optional)  
 引数の名前。 使用すると**pop**、スタックがポップされますと*セグメント名*アクティブなセグメント名になります。  
  
 *「セグメント クラス」* (省略可能)  
 Version 2.0 未満の C++ との互換性のために残されています。 これは無視されます。  
  
## <a name="example"></a>例  
  
```  
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
  
 使用して割り当てられたデータ**data_seg**その位置に関する情報は保持されません。  
  
 参照してください[/section](../build/reference/section-specify-section-attributes.md)セクションを作成するときに使用しない名前の一覧についてはします。  
  
 Const 変数のセクションを指定することもできます ([const_seg](../preprocessor/const-seg.md))、初期化されていないデータ ([bss_seg](../preprocessor/bss-seg.md))、および関数 ([code_seg](../preprocessor/code-seg.md))。  
  
## <a name="see-also"></a>関連項目  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)