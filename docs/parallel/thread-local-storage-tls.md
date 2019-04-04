---
title: 'スレッド ローカル ストレージ (TLS: Thread Local Storage)'
ms.date: 11/04/2016
helpviewer_keywords:
- multithreading [C++], Thread Local Storage
- TLS [C++]
- threading [C++], Thread Local Storage
- storing thread-specific data
- thread attribute
- Thread Local Storage [C++]
ms.assetid: 80801907-d792-45ca-b776-df0cf2e9f197
ms.openlocfilehash: f5a75f7964b0291a980b22d36e7ce6a0a87d3dc3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57293460"
---
# <a name="thread-local-storage-tls"></a>スレッド ローカル ストレージ (TLS: Thread Local Storage)

スレッド ローカル ストレージ (TLS) は、指定されたマルチスレッド プロセスの各スレッドが、スレッド固有のデータを格納する場所を割り当てるための手段です。 TLS API を使用してバインド (実行時に) スレッド固有のデータが動的にサポートされている ([TlsAlloc](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsalloc)します。  Win32 および Visual C コンパイラでは、現在、既存の API の実装に加えて、(読み込み時に) スレッドごとに静的にバインドされるデータをサポートしています。

##  <a name="_core_compiler_implementation_for_tls"></a> コンパイラによる TLS の実装

**C++ 11:**`thread_local`ストレージ クラス指定子は、スレッド ローカル ストレージ オブジェクトを指定し、クラス メンバーをお勧めします。 詳細については、[ストレージ クラス (C++)](../cpp/storage-classes-cpp.md)を参照してください。

Visual C は、Microsoft 固有の属性も用意されています。[スレッド](../cpp/thread.md)、拡張ストレージ クラス修飾子として。 使用して、 **_ _declspec**を宣言するキーワード、**スレッド**変数。 たとえば、次に示すコードは、整数型のスレッド ローカル変数を宣言して特定の値に初期化します。

```
__declspec( thread ) int tls_i = 1;
```

## <a name="rules-and-limitations"></a>規則と制約

静的にバインドされるスレッド ローカル オブジェクトと変数を宣言する場合は、次のガイドラインに従ってください。 次のガイドラインは、どちらにも適用[スレッド](../cpp/thread.md)にも、ほとんどの部分と[thread_local](../cpp/storage-classes-cpp.md):

- **スレッド**属性は、クラスとデータの宣言と定義にのみ適用できます。 関数の宣言や定義には使用できません。 たとえば、次のコードはコンパイラ エラーになります。

    ```
    __declspec( thread )void func();     // This will generate an error.
    ```

- **スレッド**修飾子をあるデータ項目にのみ指定する場合があります**静的**エクステント。 これには、グローバルなデータ オブジェクトが含まれます (どちらも**静的**と**extern**)、ローカルな静的オブジェクト、および C++ のクラスの静的データ メンバー。 自動データ オブジェクトを宣言することはできません、**スレッド**属性。 次のコードはコンパイラ エラーになります。

    ```
    void func1()
    {
        __declspec( thread )int tls_i;            // This will generate an error.
    }

    int func2(__declspec( thread )int tls_i )    // This will generate an error.
    {
        return tls_i;
    }
    ```

- 宣言と定義のスレッド ローカル オブジェクトすべて指定する必要があります、**スレッド**属性。 たとえば、次のコードはエラーになります。

    ```
    #define Thread  __declspec( thread )
    extern int tls_i;        // This will generate an error, since the
    int __declspec( thread )tls_i;        // declaration and definition differ.
    ```

- **スレッド**属性を型修飾子として使用することはできません。 たとえば、次のコードはコンパイラ エラーになります。

    ```
    char __declspec( thread ) *ch;        // Error
    ```

- C++ の宣言のオブジェクトを使用するため、**スレッド**属性は許可されて、次の 2 つの例は意味的に同等です。

    ```
    __declspec( thread ) class B
    {
    // Code
    } BObject;  // OK--BObject is declared thread local.

    class B
    {
    // Code
    };
    __declspec( thread ) B BObject;  // OK--BObject is declared thread local.
    ```

- スレッド ローカル オブジェクトのアドレスは定数とは見なされません。また、そのようなアドレスが含まれている式は、定数式とは見なされません。 標準 C では、この影響で、オブジェクトまたはポインターの初期化子としてスレッド ローカル変数のアドレスを使用することが禁止されています。 C コンパイラでは、次のコードがエラーとしてフラグが設定など。

    ```
    __declspec( thread )int tls_i;
    int *p = &tls_i;       //This will generate an error in C.
    ```

   この制限は、C++ では適用されません。 C++ ではすべてのオブジェクトを動的に初期化することが許可されているため、スレッド ローカル変数のアドレスを使用する式を使用してオブジェクトを初期化できます。 これは、スレッド ローカル オブジェクトの作成と同じように行います。 たとえば、前に示したコードが C++ ソース ファイルとしてコンパイルされる場合、エラーは発生しません。 スレッド ローカル変数のアドレスは、アドレスが取得されたスレッドが存在する限り有効であることに注意してください。

- 標準 C では、オブジェクトや変数をそれ自体への参照を含む式で初期化できます。ただし、この場合のオブジェクトは、非静的なものに限られます。 C++ では、一般的に、オブジェクト自体への参照を含む式でこのようにオブジェクトを動的に初期化できますが、この種の初期化はスレッド ローカル オブジェクトでは許可されません。 例:

    ```
    __declspec( thread )int tls_i = tls_i;                // Error in C and C++
    int j = j;                               // OK in C++, error in C
    __declspec( thread )int tls_i = sizeof( tls_i )       // Legal in C and C++
    ```

   初期化されるオブジェクトが含まれる `sizeof` 式は、そのオブジェクト自体への参照を表さないため、C と C++ の両方で有効になります。

   スレッド ローカル ストレージ機能は将来拡張される可能性があるため、C++ ではこのようにスレッド データを動的に初期化することが許可されていません。

- Windows Vista では前に、の Windows オペレーティング システムで`__declspec`(スレッド) がいくつかの制限。 DLL で任意のデータまたはオブジェクトを `__declspec`( thread ) として宣言した場合、動的に読み込まれたときに保護違反が発生する可能性があります。 によって、DLL が読み込まれた後[LoadLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibrarya)、コードで参照されるたびにシステム エラーが発生、 `__declspec`(thread) データ。 スレッドのグローバル変数領域は実行時に割り当てられるため、この領域のサイズは、アプリケーションの要件および静的にリンクされているすべての DLL の要件に基づいて計算されます。 
  `LoadLibrary` を使用すると、`__declspec`( thread ) を使用して宣言されたスレッド ローカル変数用にこの領域を拡張することはできません。 TLS の Api を使用して[TlsAlloc](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsalloc)、TLS の割り当てに DLL が読み込まれることが場合に、DLL で`LoadLibrary`します。

## <a name="see-also"></a>関連項目

[C と Win32 を使用するマルチスレッド](multithreading-with-c-and-win32.md)
