---
title: bss_seg |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.bss_seg
- bss_seg_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, bss_seg
- bss_seg pragma
ms.assetid: 755f0154-de51-4778-97d3-c9b24e445079
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b82027066e66cc51be8982a19ab6209ff236ef2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="bssseg"></a>bss_seg
初期化されていない変数が格納される .obj ファイル内のセグメントを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#pragma bss_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>コメント  
 Obj ファイルと見なすことができます、 [dumpbin](../build/reference/dumpbin-command-line.md)アプリケーションです。 初期化されていないデータの .obj ファイルの既定セグメントは、.bss です。 場合によっては、使用**bss_seg**高速化することができますを 1 つのセクションに初期化されていないデータをグループ化で、読み込み時間。  
  
 **bss_seg**パラメーターなしのセグメントを .bss にリセットします。  
  
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
// pragma_directive_bss_seg.cpp  
int i;                     // stored in .bss  
#pragma bss_seg(".my_data1")  
int j;                     // stored in "my_data1"  
  
#pragma bss_seg(push, stack1, ".my_data2")     
int l;                     // stored in "my_data2"  
  
#pragma bss_seg(pop, stack1)   // pop stack1 from stack  
int m;                     // stored in "stack_data1"  
  
int main() {  
}  
```  
  
 初期化されたデータのセクションを指定することもできます ([data_seg](../preprocessor/data-seg.md))、関数 ([code_seg](../preprocessor/code-seg.md))、および const 変数 ([const_seg](../preprocessor/const-seg.md))。  
  
 使用して割り当てられたデータ、 **bss_seg**プラグマがその位置に関する情報を保持しません。  
  
 参照してください[/section](../build/reference/section-specify-section-attributes.md)セクションを作成するときに使用しない名前の一覧についてはします。  
  
## <a name="see-also"></a>関連項目  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)