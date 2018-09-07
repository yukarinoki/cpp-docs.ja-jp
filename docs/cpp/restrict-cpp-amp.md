---
title: 制限 (C++ AMP) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- cpu_CPP
- amp_CPP
dev_langs:
- C++
helpviewer_keywords:
- restrict clause (C++ AMP)
ms.assetid: 07d3291f-7edf-456b-8828-283ac8673661
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e3385e68b7a5a112e5ff63b63afe5dd83603cf72
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678198"
---
# <a name="restrict-c-amp"></a>restrict (C++ AMP)
制限指定子は、関数宣言およびラムダ宣言に適用できます。 制限は、関数のコードに適用され、また、C++ Accelerated Massive Parallelism (C++ AMP) ランタイムを使用するアプリケーションの関数の動作に適用されます。  
  
> [!NOTE]
>  については、**制限**キーワードの一部である、 **_ _declspec**ストレージ クラス属性を参照してください[制限](../cpp/restrict.md)します。  
  
 **制限**句では、次の種類。  
  
|句|説明|  
|------------|-----------------|  
|`restrict(cpu)`|関数は C++ 言語をフルに使用できます。 restrict (cpu) 関数を使用して宣言された他の関数だけがこの関数を呼び出すことができます。|  
|`restrict(amp)`|関数は C++ AMP で高速化できる C++ 言語のサブセットのみを使用できます。|  
|連続した `restrict(cpu)` と `restrict(amp)`|関数は `restrict(cpu)` と `restrict(amp)` の両方の制約に従う必要があります。 関数は `restrict(cpu)`、`restrict(amp)`、`restrict(cpu, amp)`、または `restrict(amp, cpu)` を使用して宣言した関数から呼び出すことができます。<br /><br /> `restrict(A) restrict(B)` という形式は `restrict(A,B)` と書くことができます。|  
  
## <a name="remarks"></a>Remarks  
 **制限**キーワードは、コンテキスト キーワードです。 制限指定子の `cpu` と `amp` は予約語ではありません。 指定子の数を増やすことはできません。 ない関数、**制限**句がある関数と同じ、`restrict(cpu)`句。  
  
 `restrict(amp)` 句を持つ関数には次の制限があります。  
  
-   関数は `restrict(amp)` 句を持つ関数のみを呼び出すことができます。  
  
-   関数はインライン化できる必要があります。  
  
-   関数でのみ宣言できます**int**、**符号なし int**、 **float**、および**二重**変数、およびクラスおよびのみを含む構造体これらの型。 **bool**も許可する必要があります 4 バイト境界、複合型で使用する場合。  
  
-   ラムダ関数は、参照によってキャプチャできず、また、ポインターをキャプチャできません。  
  
-   参照と単一間接ポインターは、ローカル変数、関数の引数、戻り値の型としてのみサポートされています。  
  
-   以下は使用できません。  
  
    -   再帰  
  
    -   宣言された変数、[揮発性](../cpp/volatile-cpp.md)キーワード。  
  
    -   仮想関数  
  
    -   関数へのポインター  
  
    -   メンバー関数へのポインター  
  
    -   構造体へのポインター  
  
    -   ポインターへのポインター  
  
    -   **goto**ステートメント。  
  
    -   ラベル付きステートメント  
  
    -   **お試しください**、**キャッチ**、または**スロー**ステートメント。  
  
    -   グローバル変数  
  
    -   静的変数 使用[tile_static キーワード](../cpp/tile-static-keyword.md)代わりにします。  
  
    -   **dynamic_cast**キャストします。  
  
    -   **Typeid**演算子。  
  
    -   asm 宣言  
  
    -   可変個引数  
  
 関数の制限事項の詳細については、次を参照してください。 [(amp) の制限を制限する](https://blogs.msdn.microsoft.com/nativeconcurrency/2011/12/19/restrictamp-restrictions-part-0-of-n-introduction/)します。  
  
## <a name="example"></a>例  
 次の例は、使用する方法を示します、`restrict(amp)`句。  
  
```cpp 
void functionAmp() restrict(amp) {}   
void functionNonAmp() {}   
  
void callFunctions() restrict(amp)   
{   
    // int is allowed.  
    int x;  
    // long long int is not allowed in an amp-restricted function. This generates a compiler error.  
    // long long int y;   
  
    // Calling an amp-restricted function is allowed.  
    functionAmp();   
  
    // Calling a non-amp-restricted function is not allowed.  
    // functionNonAmp();   
}  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)