---
title: 一般的な規則と制約
ms.date: 11/04/2016
ms.assetid: 6c48902d-4259-4761-95d4-e421d69aa050
ms.openlocfilehash: 8d21f627f461dce90af93ca5c1af8c4a28098539
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213412"
---
# <a name="general-rules-and-limitations"></a>一般的な規則と制約

**Microsoft 固有の仕様**

- または属性を指定せずに関数またはオブジェクトを宣言した場合、 **`dllimport`** **`dllexport`** その関数またはオブジェクトは DLL インターフェイスの一部とは見なされません。 したがって、関数またはオブジェクトの定義は、該当のモジュール内か、同じプログラムの別のモジュール内に存在している必要があります。 関数またはオブジェクトを DLL インターフェイスの一部にするには、他のモジュール内の関数またはオブジェクトの定義をとして宣言する必要があり **`dllexport`** ます。 定義しない場合は、リンカー エラーが生成されます。

   属性を使用して関数またはオブジェクトを宣言する場合 **`dllexport`** 、その定義は、同じプログラムの一部のモジュールに記述されている必要があります。 定義しない場合は、リンカー エラーが生成されます。

- プログラム内の1つのモジュールに、 **`dllimport`** **`dllexport`** 同じ関数またはオブジェクトの宣言と宣言の両方が含まれている場合、属性は属性よりも優先され **`dllexport`** **`dllimport`** ます。 ただし、コンパイラの警告が生成されます。 次に例を示します。

    ```cpp
    __declspec( dllimport ) int i;
    __declspec( dllexport ) int i;   // Warning; inconsistent;
                                     // dllexport takes precedence.
    ```

- C++ では、グローバルに宣言されたローカルデータポインターまたは静的ローカルデータポインターを初期化することも、属性で宣言されたデータオブジェクトのアドレスで初期化することもできます。この場合 **`dllimport`** 、C ではエラーが生成されます。また、属性を使用して宣言された関数のアドレスを使用して、静的ローカル関数ポインターを初期化することもでき **`dllimport`** ます。 C では、このような代入で、関数のアドレスではなく、DLL インポート サンク (関数に制御を移すコード スタブ) のアドレスがポインターに設定されます。 C++ では、ポインターに関数のアドレスが設定されます。 次に例を示します。

    ```cpp
    __declspec( dllimport ) void func1( void );
    __declspec( dllimport ) int i;

    int *pi = &i;                             // Error in C
    static void ( *pf )( void ) = &func1;     // Address of thunk in C,
                                              // function in C++

    void func2()
    {
       static int *pi = &i;                  // Error in C
       static void ( *pf )( void ) = &func1; // Address of thunk in C,
                                             // function in C++
    }
    ```

   ただし、 **`dllexport`** オブジェクトの宣言に属性を含むプログラムは、プログラム内のどこかでそのオブジェクトの定義を提供する必要があるため、関数のアドレスを使用してグローバルまたはローカルの静的関数ポインターを初期化でき **`dllexport`** ます。 同様に、データオブジェクトのアドレスを使用して、グローバルまたはローカルの静的データポインターを初期化でき **`dllexport`** ます。 たとえば、次のコードの場合、C または C++ でエラーは発生しません。

    ```cpp
    __declspec( dllexport ) void func1( void );
    __declspec( dllexport ) int i;

    int *pi = &i;                              // Okay
    static void ( *pf )( void ) = &func1;      // Okay

    void func2()
    {
        static int *pi = &i;                   // Okay
        static void ( *pf )( void ) = &func1;  // Okay
    }
    ```

- **`dllexport`** としてマークされていない基底クラスを持つ標準クラスにを適用すると **`dllexport`** 、コンパイラによって C4275 が生成されます。

   クラス テンプレートの特殊化が基底クラスである場合、コンパイラでも同じ警告が発生します。 この問題を回避するには、基本クラスをとしてマークし **`dllexport`** ます。 クラステンプレートの特殊化に関する問題は、を配置する場所です **`__declspec(dllexport)`** 。クラステンプレートをマークすることは許可されていません。 代わりに、クラステンプレートを明示的にインスタンス化し、この明示的なインスタンス化をでマークし **`dllexport`** ます。 次に例を示します。

    ```cpp
    template class __declspec(dllexport) B<int>;
    class __declspec(dllexport) D : public B<int> {
    // ...
    ```

   この回避策は、テンプレート引数が派生クラスの場合は失敗します。 次に例を示します。

    ```cpp
    class __declspec(dllexport) D : public B<D> {
    // ...
    ```

   これはテンプレートの一般的なパターンなので、コンパイラは、 **`dllexport`** 1 つまたは複数の基底クラスを持つクラスに適用された場合、および1つ以上の基底クラスがクラステンプレートの特殊化である場合に、のセマンティクスを変更しました。 この場合、コンパイラは **`dllexport`** クラステンプレートの特殊化に暗黙的に適用されます。 警告が表示されない場合は、次の操作を実行できます。

    ```cpp
    class __declspec(dllexport) D : public B<D> {
    // ...
    ```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[dllexport、dllimport](../cpp/dllexport-dllimport.md)
