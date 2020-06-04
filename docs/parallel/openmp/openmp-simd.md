---
title: SIMD 拡張命令
ms.date: 03/20/2019
helpviewer_keywords:
- SIMD
- OpenMP in Visual C++, new features
- explicit parallelization, new features
ms.openlocfilehash: 0a7f1142a3a432628795341f4885b76a5c144990
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366450"
---
# <a name="simd-extension"></a>SIMD 拡張命令

Visual C++ は現在、OpenMP 2.0 標準をサポートしますが、現在では、Visual Studio 2019 には SIMD 機能も用意されています。

> [!NOTE]
> SIMD を使用するには、スイッチ`-openmp:experimental`を使用する場合に使用できない追加の OpenMP`-openmp`機能を有効にするスイッチを使用してコンパイルします。
>
> スイッチ`-openmp:experimental`は`-openmp`、すべての OpenMP 2.0 機能が使用に含まれていることを意味します。

詳細については、「 [C++ OpenMP の SIMD 拡張機能 」を参照](https://devblogs.microsoft.com/cppblog/simd-extension-to-c-openmp-in-visual-studio/)してください。

## <a name="openmp-simd-in-visual-c"></a>ビジュアル C++ でのオープン MP SIMD

OpenMP 4.0 規格で導入された OpenMP SIMD は、ベクトルに優しいループを作るターゲットです。 ループの前`simd`にディレクティブを使用することで、コンパイラはベクトルの依存関係を無視し、可能な限りベクトルに優しくループを作成し、複数のループ反復を同時に実行するユーザーの意図を尊重することができます。

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

Visual C++ は、同様の非 OpenMP`#pragma vector`ループ`#pragma ivdep`プラグマを提供し、 と同様に、 OpenMP SIMD を使用すると、コンパイラは次のように、より多くのことができます。

- 常に現在のベクターの依存関係を無視できます。
- `/fp:fast`ループ内で有効になります。
- 関数呼び出しを使用した外部ループとループは、ベクトルに優しいものです。
- ネストされたループは、1つのループに合体し、ベクトルにやさしいものにすることができます。
- ハイブリッド加速により`#pragma omp for simd`、粗粒度のマルチスレッド化ときめ細かいベクトルを実現。  

ベクトルフレンドリーなループの場合、ベクトルサポートログスイッチを使用しない限り、コンパイラはサイレントのままです。

```cmd
    cl -O2 -openmp:experimental -Qvec-report:2 mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(96) : info C5001: Omp simd loop vectorized
```

ベクトルに優しくないループの場合、コンパイラは各メッセージを発行します。

```cmd
    cl -O2 -openmp:experimental mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
```

### <a name="clauses"></a>句

OpenMP SIMD ディレクティブは、ベクトルサポートを強化するために以下の節を取ることもできます。

|ディレクティブ|説明|
|---|---|
|`simdlen(length)`|ベクトルレーンの数を指定します。|
|`safelen(length)`|ベクトルの依存関係の距離を指定します。|
|`linear(list[ : linear-step]`)|ループ誘導変数から配列サブスクリプションへの線形マッピング。|
|`aligned(list[ : alignment])`|データの配置。|
|`private(list)`|データの民営化を指定します。|
|`lastprivate(list)`|最後のイテレーションの最終値を使用してデータの民営化を指定します。|
|`reduction(reduction-identifier:list)`|カスタマイズされた縮小操作を指定します。|
|`collapse(n)`|ループの結合|

> [!NOTE]
> 非有効な SIMD 句は、コンパイラによって解析され、警告を伴って無視されます。
>
> たとえば、次のコードを使用すると警告が発行されます。
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
  
OpenMP SIMD ディレクティブは、コンパイラがループをベクトルに対応させる方法をユーザーに提供します。 OpenMP SIMD ディレクティブを使用してループにコメントを付けると、ユーザーは複数のループ反復を同時に実行する予定です。

たとえば、次のループは OpenMP SIMD ディレクティブでアポイントされています。 a[i] から a[i-1] への後方依存関係があるため、ループ反復の間で完全な並列処理はありませんが、SIMD ディレクティブにより、コンパイラは最初のステートメントの連続反復を 1 つのベクトル命令にパックし、並列実行することができます。

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

したがって、次の変換されたベクトル形式のループは、コンパイラが元のループ反復の連続した動作を保持するため **、有効**です。 つまり`a[i]`、後に`a[-1]`実行され`b[i]``a[i]`、呼び出しが最後に`bar`発生します。

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

または でエイリアス`a[i]`を使用する可能性がある場合`*c`、メモリ参照をループから移動**することは合法ではありません。** `b[i]` また、1 つの元のイテレーション内でステートメントが順次依存関係を解除した場合に、ステートメントを並べ替えることもできます。 たとえば、次の変換されたループは有効ではありません。

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
