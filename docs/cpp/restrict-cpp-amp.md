---
title: restrict (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- cpu_CPP
- amp_CPP
helpviewer_keywords:
- restrict clause (C++ AMP)
ms.assetid: 07d3291f-7edf-456b-8828-283ac8673661
ms.openlocfilehash: 5a0011d11e4a59c9ca3a5e18f44d4cf831b21582
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366653"
---
# <a name="restrict-c-amp"></a>restrict (C++ AMP)

制限指定子は、関数宣言およびラムダ宣言に適用できます。 制限は、関数のコードに適用され、また、C++ Accelerated Massive Parallelism (C++ AMP) ランタイムを使用するアプリケーションの関数の動作に適用されます。

> [!NOTE]
> **__declspec**ストレージ・クラス属性の一部である**restrict**キーワードについては、 [restrict](../cpp/restrict.md)を参照してください。

**restrict**句は次の形式をとります。

|句|説明|
|------------|-----------------|
|`restrict(cpu)`|関数は C++ 言語をフルに使用できます。 restrict (cpu) 関数を使用して宣言された他の関数だけがこの関数を呼び出すことができます。|
|`restrict(amp)`|関数は C++ AMP で高速化できる C++ 言語のサブセットのみを使用できます。|
|連続した `restrict(cpu)` と `restrict(amp)`|関数は `restrict(cpu)` と `restrict(amp)` の両方の制約に従う必要があります。 関数は `restrict(cpu)`、`restrict(amp)`、`restrict(cpu, amp)`、または `restrict(amp, cpu)` を使用して宣言した関数から呼び出すことができます。<br /><br /> `restrict(A) restrict(B)` という形式は `restrict(A,B)` と書くことができます。|

## <a name="remarks"></a>解説

**restrict**キーワードはコンテキスト キーワードです。 制限指定子の `cpu` と `amp` は予約語ではありません。 指定子の数を増やすことはできません。 **restrict**句を持たない関数は、`restrict(cpu)`句を持つ関数と同じです。

`restrict(amp)` 句を持つ関数には次の制限があります。

- 関数は `restrict(amp)` 句を持つ関数のみを呼び出すことができます。

- 関数はインライン化できる必要があります。

- 関数は **、int**、**符号なし int** **、float**、**および double**変数、およびこれらの型のみを含むクラスと構造体のみを宣言できます。 **bool**も許可されますが、複合型で使用する場合は 4 バイトで整列する必要があります。

- ラムダ関数は、参照によってキャプチャできず、また、ポインターをキャプチャできません。

- 参照と単一間接ポインターは、ローカル変数、関数の引数、戻り値の型としてのみサポートされています。

- 以下は使用できません。

  - 再帰

  - [volatile](../cpp/volatile-cpp.md)キーワードで宣言された変数。

  - 仮想関数

  - 関数へのポインター

  - メンバー関数へのポインター

  - 構造体へのポインター

  - ポインターへのポインター

  - **goto**ステートメント。

  - ラベル付きステートメント

  - **を試す**、**キャッチ**、 または**ステートメントをスロー**する。

  - グローバル変数

  - 静的変数 代わりに[tile_staticキーワードを](../cpp/tile-static-keyword.md)使用してください。

  - **dynamic_cast**キャスト。

  - **typeid**演算子。

  - asm 宣言

  - 可変個引数

機能の制限については、[制限 (amp) の制限](https://blogs.msdn.microsoft.com/nativeconcurrency/2011/12/19/restrictamp-restrictions-part-0-of-n-introduction/)を参照してください。

## <a name="example"></a>例

句の使用方法を次の例に`restrict(amp)`示します。

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
