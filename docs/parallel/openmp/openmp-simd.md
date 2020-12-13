---
description: ': SIMD 拡張機能についての詳細情報'
title: SIMD 拡張命令
ms.date: 03/20/2019
helpviewer_keywords:
- SIMD
- OpenMP in Visual C++, new features
- explicit parallelization, new features
ms.openlocfilehash: 58a3f29002c4e517a2019454dfe741dfb5352a3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342427"
---
# <a name="simd-extension"></a>SIMD 拡張命令

現在、Visual C++ では OpenMP 2.0 標準がサポートされていますが、Visual Studio 2019 には SIMD 機能も用意されています。

> [!NOTE]
> SIMD を使用するには、スイッチを使用する `-openmp:experimental` ときに使用できない追加の OpenMP 機能を有効にするスイッチを使用してコンパイルし `-openmp` ます。
>
> `-openmp:experimental`スイッチ subsumes `-openmp` 。これは、すべての OpenMP 2.0 機能が使用されることを意味します。

詳細については、「 [Visual Studio での C++ OpenMP の SIMD 拡張」を](https://devblogs.microsoft.com/cppblog/simd-extension-to-c-openmp-in-visual-studio/)参照してください。

## <a name="openmp-simd-in-visual-c"></a>Visual C++ の OpenMP SIMD

Openmp SIMD は、OpenMP 4.0 標準で導入され、ベクターを使いやすくするループを作成しています。 ループの前にディレクティブを使用することにより、 `simd` コンパイラはベクターの依存関係を無視し、可能な限りベクトルをわかりやすくすることができます。また、複数のループの反復が同時に実行されることをユーザーの意図として考慮します。

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

Visual C++ には、やのような OpenMP 以外のループプラグマが `#pragma vector` `#pragma ivdep` ありますが、openmp SIMD を使用すると、コンパイラは次のような処理を行うことができます。

- 現在のベクター依存関係を無視することは常に許可されています。
- `/fp:fast` は、ループ内で有効になっています。
- 外側のループと関数呼び出しを使用したループは、ベクターを使いやすくします。
- 入れ子になったループは、1つのループに結合して、ベクターを使いやすくすることができます。
- を使用したハイブリッド高速化。粒度 `#pragma omp for simd` の粗いマルチスレッドおよび粒度の細かいベクターを実現します。  

ベクター対応のループの場合、ベクター対応のログスイッチを使用しない限り、コンパイラはサイレント状態のままです。

```cmd
    cl -O2 -openmp:experimental -Qvec-report:2 mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(96) : info C5001: Omp simd loop vectorized
```

ベクターを使用しないループの場合、コンパイラは各メッセージを発行します。

```cmd
    cl -O2 -openmp:experimental mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
```

### <a name="clauses"></a>句

OpenMP SIMD ディレクティブは、次の句を使用してベクターのサポートを強化することもできます。

|ディレクティブ|説明|
|---|---|
|`simdlen(length)`|ベクターレーンの数を指定します。|
|`safelen(length)`|ベクター依存関係の距離を指定します。|
|`linear(list[ : linear-step]`)|ループから配列への変換変数に対する線形マッピング。|
|`aligned(list[ : alignment])`|データの配置。|
|`private(list)`|Data 民営化を指定します。|
|`lastprivate(list)`|最後のイテレーションからの最終的な値を使用してデータ民営化を指定します。|
|`reduction(reduction-identifier:list)`|カスタマイズされたリダクション操作を指定します。|
|`collapse(n)`|ループの入れ子を結合します。|

> [!NOTE]
> 非効率的な SIMD 句は解析され、コンパイラによって警告として無視されます。
>
> たとえば、次のコードを使用すると、警告が発行されます。
>
> ```c
>    #pragma omp simd simdlen(8)
>    for (i = 0; i < count; i++)
>    {
>        a[i] = a[i-1] + 1;
>        b[i] = *c + 1;
>        bar(i);
>    }
> ```
>
> ```Output
>    warning C4849: OpenMP 'simdlen' clause ignored in 'simd' directive
> ```

### <a name="example"></a>例
  
OpenMP SIMD ディレクティブを使用すると、コンパイラのループベクターをわかりやすくすることができます。 OpenMP SIMD ディレクティブを使用してループに注釈を付けることにより、複数のループイテレーションを同時に実行することを意図しています。

たとえば、次のループには、OpenMP SIMD ディレクティブで注釈が付けられています。 ループの反復の間に完全な並列処理はありません。 [i] から [i-1] への下位依存関係がありますが、SIMD ディレクティブにより、コンパイラは、最初のステートメントの連続する反復を1つのベクター命令にまとめて、並列で実行することができます。

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

したがって、ループの次の変換されたベクター形式は **有効** です。コンパイラは、元のループの反復処理ごとに順次動作を維持するためです。 つまり、はの `a[i]` 後に実行され、はの後に実行され、の `a[-1]` `b[i]` `a[i]` 呼び出しは `bar` 最後に行われます。

```c
    for (i = 0; i < count; i+=4)
    {
        a[i:i+3] = a[i-1:i+2] + 1;
        b[i:i+3] = *c + 1;
        bar(i);
        bar(i+1);
        bar(i+2);
        bar(i+3);
    }
```

またはで別名を付けることができる場合、ループからメモリ参照を移動するのは有効では **ありません** `*c` `a[i]` `b[i]` 。 また、シーケンシャルな依存関係が失われた場合に、1つのイテレーション内でステートメントの順序を変更することもできません。 たとえば、次の変換されたループは無効です。

```c
    c = b;
    t = *c;
    for (i = 0; i < count; i+=4)
    {
        a[i:i+3] = a[i-1:i+2] + 1;
        bar(i);            // illegal to reorder if bar[i] depends on b[i]
        b[i:i+3] = t + 1;  // illegal to move *c out of the loop
        bar(i+1);
        bar(i+2);
        bar(i+3);
    }
```

## <a name="see-also"></a>関連項目

[/openmp (OpenMP 2.0 サポートの有効化)](../../build/reference/openmp-enable-openmp-2-0-support.md)<br/>
