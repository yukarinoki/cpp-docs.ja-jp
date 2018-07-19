---
title: パラメーターの引き渡し |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e838ee5f-c2fe-40b0-9a23-8023c949c820
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ec0c5b6fe00430c8b08fefdd8781b677004085e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369358"
---
# <a name="parameter-passing"></a>パラメーターの引き渡し
最初の 4 つの整数引数は、レジスタに渡されます。 整数値は、RCX、RDX、R8、R9 で (左右からの順序) で渡されます。 引数 5 以上、スタックに渡されます。 すべての引数はレジスタ内で右揃えがします。 場合、呼び出し先は、レジスタの上位ビットを無視できますので、これを行う必要があり、レジスタの必要な部分のみアクセスできます。  
  
 倍精度の浮動小数点引数は XMM0 で - (最大 4) とは、通常使用されるカーディナル スロットの整数スロット (RCX、RDX、R8、R9) XMM3 (例を参照) を無視して、その逆です。  
  
 [_ _m128](../cpp/m128.md)型、配列と文字列がイミディ エイト値によって渡されることはありませんが、呼び出し元が割り当てたメモリへのポインターが渡されるではなく、します。 場合、同じサイズの整数と同様に、サイズ 8、16、32、または 64 ビットと _ _m64 の構造体/共用体が渡されます。 これらのサイズ以外の構造体/共用体は、呼び出し元が割り当てたメモリへのポインターとして渡されます。 これらの集約型に対するポインターとして渡されます (含む\__m128)、呼び出し元が割り当てたの一時的なメモリが 16 バイトでアラインされます。  
  
 スタック領域を割り当てないし、その他の関数を呼び出す必要はありませんの組み込み関数は、コンパイラと組み込み関数の実装の間に強力なバインディングがあるため、追加のレジスタ引数を渡す他の volatile レジスタを使用できます。 これは、パフォーマンスを向上させるためさらに営業案件です。  
  
 呼び出し先は、必要な場合は、そのシャドウ領域レジスタ パラメーターのダンプの責任を持ちます。  
  
 次の表では、パラメーターを渡す方法をまとめたものです。  
  
|パラメーターの型|どのように渡されました。|  
|--------------------|----------------|  
|浮動小数点数|最初に 4 つのパラメーター - XMM3 を通じて XMM0 です。 他のユーザーは、スタックに渡されます。|  
|整数型|最初に 4 つのパラメーター - RCX、RDX、R8、R9。 他のユーザーは、スタックに渡されます。|  
|集計 (8、16、32、または 64 ビット) および _ _m64|最初に 4 つのパラメーター - RCX、RDX、R8、R9。 他のユーザーは、スタックに渡されます。|  
|集計 (その他)|指すポインターです。 まず 4 つのパラメーターは RCX、RDX、R8、R9 でポインターとして渡されます。|  
|__m128|指すポインターです。 まず 4 つのパラメーターは RCX、RDX、R8、R9 でポインターとして渡されます。|  
  
## <a name="example-of-argument-passing-1---all-integers"></a>1 - すべての整数値を渡す引数の例  
  
```  
func1(int a, int b, int c, int d, int e);    
// a in RCX, b in RDX, c in R8, d in R9, e pushed on stack  
```  
  
## <a name="example-of-argument-passing-2---all-floats"></a>2 - すべての浮動小数点値を渡す引数の例  
  
```  
func2(float a, double b, float c, double d, float e);    
// a in XMM0, b in XMM1, c in XMM2, d in XMM3, e pushed on stack  
```  
  
## <a name="example-of-argument-passing-3---mixed-ints-and-floats"></a>3 - 混在整数と浮動小数点値を渡す引数の例  
  
```  
func3(int a, double b, int c, float d);    
// a in RCX, b in XMM1, c in R8, d in XMM3  
```  
  
## <a name="example-of-argument-passing-4--m64-m128-and-aggregates"></a>引数渡し 4 の例-_ _m64、 \__m128、および集計  
  
```  
func4(__m64 a, _m128 b, struct c, float d);  
// a in RCX, ptr to b in RDX, ptr to c in R8, d in XMM3  
```  
  
## <a name="see-also"></a>関連項目  
 [呼び出し規則](../build/calling-convention.md)