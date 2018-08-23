---
title: bss_seg |Microsoft Docs
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
ms.openlocfilehash: 08304a42b961f93b7d9e4e6e644e1514e34eb335
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2018
ms.locfileid: "42540197"
---
# <a name="bssseg"></a>bss_seg
初期化されていない変数が格納される .obj ファイル内のセグメントを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma bss_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## <a name="remarks"></a>Remarks  
 
Obj ファイルを表示できる、 [dumpbin](../build/reference/dumpbin-command-line.md)アプリケーション。 初期化されていないデータの .obj ファイルの既定セグメントは、.bss です。 場合によっては使用**bss_seg**高速化できますの読み込み時間の 1 つのセクションに初期化されていないデータをグループ化します。  
  
**bss_seg**パラメーターなしで、セグメントを .bss にリセットします。  
  
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
  
データを使用して割り当て、 **bss_seg**プラグマがその場所に関する情報を保持していません。  
  
参照してください[/section](../build/reference/section-specify-section-attributes.md)に対して一連の名前のセクションを作成するときに使用する必要があります。  
  
## <a name="see-also"></a>関連項目  
 
[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)