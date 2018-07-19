---
title: パック |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- pack_CPP
- vc-pragma.pack
dev_langs:
- C++
helpviewer_keywords:
- pragmas, pack
- pack pragma
ms.assetid: e4209cbb-5437-4b53-b3fe-ac264501d404
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6c29c31cae2b7de59d4db5ed6546ad4eda6baecf
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33843627"
---
# <a name="pack"></a>pack
構造体メンバー、共用体メンバー、およびクラス メンバーのパッキング アラインメントを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#pragma pack( [ show ] | [ push | pop ] [, identifier ] , n  )  
```  
  
## <a name="remarks"></a>コメント  
 クラスをパッキングすると、そのメンバーはメモリ内で互いの直後に配置されます。そのため、一部またはすべてのメンバーがターゲット アーキテクチャの既定のアラインメントより小さい境界内にアラインされる場合があります。 `pack` では、データ宣言レベルで制御できます。 これは、コンパイラ オプションは異なります[/Zp](../build/reference/zp-struct-member-alignment.md)、モジュール レベルの制御のみを提供します。 `pack` は、プラグマが参照された後の最初の `struct`、`union`、または `class` 宣言で有効になります。 `pack` は、定義への影響はありません。 呼び出す`pack`引数セットなしで`n`コンパイラ オプションで設定された値に **/Zp**です。 コンパイラ オプションを設定しない場合、既定値は 8 になります。  
  
 構造体の配置を変更すると、メモリの領域はそれほど使用されていなくても、パフォーマンスが低下したり、アラインメントされていないアクセスについてハードウェアで生成された例外を受け取る場合があります。  使用してこの例外の動作を変更することができます[SetErrorMode](http://msdn.microsoft.com/library/windows/desktop/ms680621)です。  
  
 **表示**(省略可能)  
 パッキング アラインメントの現在のバイト値を表示します。 値は警告メッセージによって表示されます。  
  
 **プッシュ**(省略可能)  
 現在のパッキング アラインメント値を内部コンパイラ スタックにプッシュし、現在のパッキング アラインメント値を `n` に設定します。 `n` が指定されていない場合、現在のパッキング アラインメントの値がプッシュされます。  
  
 **pop** (省略可能)  
 内部コンパイラ スタックの最上部からレコードを削除します。 場合`n`が指定されない**pop**スタックの一番上の結果のレコードに関連付けられているパッキング値は、新しいパッキング アラインメント値。 `n` が指定されている場合、たとえば `#pragma pack(pop, 16)` では、`n` が新しいパッキング アラインメント値になります。 `identifier` (たとえば `#pragma pack(pop, r1)`) でポップすると、スタック内のすべてのレコードが `identifier` のあるレコードまでポップされます。 このレコードがポップされ、スタックの最上位の結果のレコードに関連付けられているパッキング値が新しいパッキング アラインメント値になります。 ポップすると場合、`identifier`のどのレコード、スタックにでもない、 **pop**は無視されます。  
  
 `identifier` (省略可能)  
 使用すると**プッシュ**、内部コンパイラ スタックのレコードに名前が割り当てられます。 使用すると**pop**、レコードまで内部スタックからポップ`identifier`が削除された場合`identifier`がない内部スタックで、何もポップします。  
  
 `n` (省略可能)  
 パッキングに使用される値 (バイト単位) を指定します。 場合、コンパイラ オプション[/Zp](../build/reference/zp-struct-member-alignment.md)モジュールの既定値が設定されていない`n`は 8 です。 有効値は 1、2、4、8、および 16 です。 メンバーのアラインメントは、`n` の倍数またはメンバーのサイズの倍数の小さい方の境界上にあります。  
  
 `#pragma pack(pop, identifier, n)` 定義されていません。  
  
 アラインメントの変更方法の詳細については、次のトピックを参照してください。  
  
-   [__alignof](../cpp/alignof-operator.md)  
  
-   [align](../cpp/align-cpp.md)  
  
-   [__unaligned](../cpp/unaligned.md)  
  
-   [構造体の配置例](../build/examples-of-structure-alignment.md)(x64 固有)  
  
    > [!WARNING]
    >  Visual Studio 2015 以降では、標準の alignas および alignof 演算子を使用できることに注意してください。これらは `__alignof` および `declspec( align )` とは異なり、コンパイラ間で移植できます。 C++ 標準はパッキングに対応していないため、ターゲット アーキテクチャのワード サイズより小さいアラインメントを指定するには、まだ `pack` (または他のコンパイラでの対応する拡張機能) を使用する必要があります。  
  
## <a name="example"></a>例  
 次のサンプルでは、`pack` プラグマを使用して、構造体のアラインメントを変更する方法を示します。  
  
```  
// pragma_directives_pack.cpp  
#include <stddef.h>  
#include <stdio.h>  
  
struct S {  
   int i;   // size 4  
   short j;   // size 2  
   double k;   // size 8  
};  
  
#pragma pack(2)  
struct T {  
   int i;  
   short j;  
   double k;  
};  
  
int main() {  
   printf("%zu ", offsetof(S, i));  
   printf("%zu ", offsetof(S, j));  
   printf("%zu\n", offsetof(S, k));  
  
   printf("%zu ", offsetof(T, i));  
   printf("%zu ", offsetof(T, j));  
   printf("%zu\n", offsetof(T, k));  
}  
```  
  
```  
0 4 8  
0 4 6  
```  
  
## <a name="example"></a>例  
 次の例を使用する方法を示しています、**プッシュ**、 **pop**、および**表示**構文です。  
  
```  
// pragma_directives_pack_2.cpp  
// compile with: /W1 /c  
#pragma pack()   // n defaults to 8; equivalent to /Zp8  
#pragma pack(show)   // C4810  
#pragma pack(4)   // n = 4  
#pragma pack(show)   // C4810  
#pragma pack(push, r1, 16)   // n = 16, pushed to stack  
#pragma pack(show)   // C4810  
#pragma pack(pop, r1, 2)   // n = 2 , stack popped  
#pragma pack(show)   // C4810  
```  
  
## <a name="see-also"></a>関連項目  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)