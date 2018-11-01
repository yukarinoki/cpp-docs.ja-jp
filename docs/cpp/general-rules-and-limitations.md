---
title: 一般的な規則と制約
ms.date: 11/04/2016
ms.assetid: 6c48902d-4259-4761-95d4-e421d69aa050
ms.openlocfilehash: 931ae04ef47262f15d037a2b5eeb35bd01a8419d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439231"
---
# <a name="general-rules-and-limitations"></a>一般的な規則と制約

## <a name="microsoft-specific"></a>Microsoft 固有の仕様

- 関数を宣言するか、またはなしオブジェクトの場合、 **dllimport**または**dllexport**属性、関数またはオブジェクトは DLL インターフェイスの一部を考慮されません。 したがって、関数またはオブジェクトの定義は、該当のモジュール内か、同じプログラムの別のモジュール内に存在している必要があります。 DLL インターフェイスの関数またはオブジェクトの一部にするには、関数またはその他のモジュールでのオブジェクトの定義を宣言する必要があります**dllexport**します。 定義しない場合は、リンカー エラーが生成されます。

   関数を宣言するか、またはオブジェクトの場合、 **dllexport**属性は、その定義は、同じプログラムの一部のモジュールに表示する必要があります。 定義しない場合は、リンカー エラーが生成されます。

- プログラムで 1 つのモジュールには、両方が含まれている場合**dllimport**と**dllexport**同じ関数またはオブジェクトの宣言、 **dllexport**属性が優先されます経由で、 **dllimport**属性。 ただし、コンパイラの警告が生成されます。 例えば:

    ```cpp
    __declspec( dllimport ) int i;
    __declspec( dllexport ) int i;   // Warning; inconsistent;
                                     // dllexport takes precedence.
    ```

- C++ では、グローバルに宣言または静的ローカル データ ポインターを初期化することができますかで宣言されたデータ オブジェクトのアドレスを持つ、 **dllimport**属性には、c 言語でエラーが生成されますさらで宣言された関数のアドレスで静的なローカル関数ポインターを初期化することができます、 **dllimport**属性。 C では、このような代入で、関数のアドレスではなく、DLL インポート サンク (関数に制御を移すコード スタブ) のアドレスがポインターに設定されます。 C++ では、ポインターに関数のアドレスが設定されます。 例えば:

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

   ただし、プログラムを含むため、 **dllexport**オブジェクトの宣言の属性では、プログラムのどこかにそのオブジェクトの定義を提供する必要があります、グローバルまたはローカルの静的関数ポインターを初期化することができますアドレスを**dllexport**関数。 同様に、グローバルまたはローカルの静的データ ポインターのアドレスを初期化することができます、 **dllexport**データ オブジェクト。 たとえば、次のコードの場合、C または C++ でエラーは発生しません。

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

- 適用した場合**dllexport**としてマークされていない基底クラスを含む通常のクラスに**dllexport**、コンパイラで C4275 が生成されます。

   クラス テンプレートの特殊化が基底クラスである場合、コンパイラでも同じ警告が発生します。 これを回避するには、基底クラスにマークを付ける**dllexport**します。 クラス テンプレートの特殊化の問題は、配置する場所、**方式**; クラス テンプレートをマークすることはできません。 代わりに、明示的にクラス テンプレートのインスタンスを作成し、この明示的なインスタンス化をマーク**dllexport**します。 例えば:

    ```cpp
    template class __declspec(dllexport) B<int>;
    class __declspec(dllexport) D : public B<int> {
    // ...
    ```

   この回避策は、テンプレート引数が派生クラスの場合は失敗します。 例えば:

    ```cpp
    class __declspec(dllexport) D : public B<D> {
    // ...
    ```

   コンパイラのセマンティクスが変更されたテンプレートでの一般的なパターンであるため**dllexport**を 1 つまたは複数の基底クラスを持つクラスに適用されたとき、および 1 つ以上の基底クラスはクラス テンプレートの特殊化. コンパイラが暗黙的に適用されますこの場合、 **dllexport**クラス テンプレートの特殊化します。 次のでき、警告は表示されません。

    ```cpp
    class __declspec(dllexport) D : public B<D> {
    // ...
    ```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[dllexport、dllimport](../cpp/dllexport-dllimport.md)