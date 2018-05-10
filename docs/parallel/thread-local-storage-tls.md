---
title: スレッド ローカル ストレージ (TLS) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- multithreading [C++], Thread Local Storage
- TLS [C++]
- threading [C++], Thread Local Storage
- storing thread-specific data
- thread attribute
- Thread Local Storage [C++]
ms.assetid: 80801907-d792-45ca-b776-df0cf2e9f197
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c4cd0897a04ec2e07f1f8f3b660d092e0075ac0b
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="thread-local-storage-tls"></a>スレッド ローカル ストレージ (TLS: Thread Local Storage)
スレッド ローカル ストレージ (TLS) は、指定されたマルチスレッド プロセスの各スレッドが、スレッド固有のデータを格納する場所を割り当てるための手段です。 TLS API を使用してバインド (実行時) のスレッドに固有のデータを動的にサポート ([TlsAlloc](https://msdn.microsoft.com/en-us/library/windows/desktop/ms686801)、 [TlsGetValue](https://msdn.microsoft.com/en-us/library/windows/desktop/ms686812)、 [TlsSetValue](https://msdn.microsoft.com/en-us/library/windows/desktop/ms686818)、および[TlsFree](https://msdn.microsoft.com/en-us/library/windows/desktop/ms686804)). Windows にスレッド ローカル ストレージを実装する方法の詳細については、次を参照してください。[スレッド ローカル ストレージ (Windows)](https://msdn.microsoft.com/en-us/library/windows/desktop/ms686749\(v=vs.85\).aspx)です。  Win32 および Visual C コンパイラでは、現在、既存の API の実装に加えて、(読み込み時に) スレッドごとに静的にバインドされるデータをサポートしています。  
  
##  <a name="_core_compiler_implementation_for_tls"></a> コンパイラによる TLS の実装  
 **C++ 11:** 、`thread_local`ストレージ クラス指定子は、スレッド ローカル ストレージ オブジェクトを指定し、クラス メンバーのことをお勧めします。 詳細については、次を参照してください。[ストレージ クラス (C++)](../cpp/storage-classes-cpp.md)です。  
  
 Visual C は、Microsoft 固有の属性も用意されています。[スレッド](../cpp/thread.md)、拡張ストレージ クラス修飾子として。 使用して、`__declspec`を宣言するキーワード、**スレッド**変数。 たとえば、次に示すコードは、整数型のスレッド ローカル変数を宣言して特定の値に初期化します。  
  
```  
__declspec( thread ) int tls_i = 1;  
```  
  
## <a name="rules-and-limitations"></a>規則と制約  
 静的にバインドされるスレッド ローカル オブジェクトと変数を宣言する場合は、次のガイドラインに従ってください。 次のガイドラインは、どちらにも適用[スレッド](../cpp/thread.md)とに、ほとんどの部分も[thread_local](../cpp/storage-classes-cpp.md):  
  
-   `thread` 属性は、クラスとデータの宣言と定義にのみ適用できます。 関数の宣言や定義には使用できません。 たとえば、次のコードはコンパイラ エラーになります。  
  
    ```  
  
    __declspec( thread )void func();     // This will generate an error.  
    ```  
  
-   `thread` 修飾子は、エクステントが `static` のデータ項目のみで指定される場合があります。 これには、グローバルなデータ オブジェクト (`static` と `extern` の両方)、ローカルな静的オブジェクト、C++ クラスの静的データ メンバーが含まれます。 自動データ オブジェクトは、`thread` 属性を使用して宣言できません。 次のコードはコンパイラ エラーになります。  
  
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
  
-   スレッド ローカル オブジェクトの宣言と定義では、すべて `thread` 属性を指定する必要があります。 たとえば、次のコードはエラーになります。  
  
    ```  
    #define Thread  __declspec( thread )  
    extern int tls_i;        // This will generate an error, since the  
    int __declspec( thread )tls_i;        // declaration and definition differ.  
    ```  
  
-   `thread` 属性は型修飾子として使用できません。 たとえば、次のコードはコンパイラ エラーになります。  
  
    ```  
    char __declspec( thread ) *ch;        // Error  
    ```  
  
-   `thread` 属性を使用する C++ オブジェクトの宣言は許可されるので、次の 2 つの例は同じ意味になります。  
  
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
  
-   スレッド ローカル オブジェクトのアドレスは定数とは見なされません。また、そのようなアドレスが含まれている式は、定数式とは見なされません。 標準 C では、この影響で、オブジェクトまたはポインターの初期化子としてスレッド ローカル変数のアドレスを使用することが禁止されています。 C コンパイラでは、次のコードがエラーとしてフラグが立てなど。  
  
    ```  
  
    __declspec( thread )int tls_i;  
    int *p = &tls_i;       //This will generate an error in C.  
    ```  
  
     この制限は、C++ では適用されません。 C++ ではすべてのオブジェクトを動的に初期化することが許可されているため、スレッド ローカル変数のアドレスを使用する式を使用してオブジェクトを初期化できます。 これは、スレッド ローカル オブジェクトの作成と同じように行います。 たとえば、前に示したコードが C++ ソース ファイルとしてコンパイルされる場合、エラーは発生しません。 スレッド ローカル変数のアドレスは、アドレスが取得されたスレッドが存在する限り有効であることに注意してください。  
  
-   標準 C では、オブジェクトや変数をそれ自体への参照を含む式で初期化できます。ただし、この場合のオブジェクトは、非静的なものに限られます。 C++ では、一般的に、オブジェクト自体への参照を含む式でこのようにオブジェクトを動的に初期化できますが、この種の初期化はスレッド ローカル オブジェクトでは許可されません。 例えば:  
  
    ```  
    __declspec( thread )int tls_i = tls_i;                // Error in C and C++   
    int j = j;                               // OK in C++, error in C  
    __declspec( thread )int tls_i = sizeof( tls_i )       // Legal in C and C++  
    ```  
  
     初期化されるオブジェクトが含まれる `sizeof` 式は、そのオブジェクト自体への参照を表さないため、C と C++ の両方で有効になります。  
  
     スレッド ローカル ストレージ機能は将来拡張される可能性があるため、C++ ではこのようにスレッド データを動的に初期化することが許可されていません。  
  
-   Windows Vista より前に、の Windows オペレーティング システムで`__declspec`(スレッド) がいくつかの制限。 DLL で任意のデータまたはオブジェクトを `__declspec`( thread ) として宣言した場合、動的に読み込まれたときに保護違反が発生する可能性があります。 によって、DLL が読み込まれた後[LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175)、コードで参照されるたびにシステム エラーが発生、 `__declspec`(thread) データ。 スレッドのグローバル変数領域は実行時に割り当てられるため、この領域のサイズは、アプリケーションの要件および静的にリンクされているすべての DLL の要件に基づいて計算されます。 `LoadLibrary` を使用すると、`__declspec`( thread ) を使用して宣言されたスレッド ローカル変数用にこの領域を拡張することはできません。 など、TLS Api を使用して[TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801)、TLS を割り当ててに DLL が読み込まれている可能性がある場合、DLL で`LoadLibrary`です。  
  
## <a name="see-also"></a>関連項目  
 [C と Win32 を使用するマルチスレッド](../parallel/multithreading-with-c-and-win32.md)   
