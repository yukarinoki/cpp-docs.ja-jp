---
title: '方法: WRL を使用して従来の COM コンポーネントを作成する'
description: Windows ランタイム C++ テンプレートライブラリ (WRL) を使用して、デスクトップアプリで使用する基本的なクラシック COM コンポーネントを作成します。
ms.date: 10/23/2020
ms.topic: reference
ms.openlocfilehash: 417c2e4635b380717662fa0762062f0228659de4
ms.sourcegitcommit: bf54b407169900bb668c85a67b31dbc0f069fe65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92497198"
---
# <a name="how-to-create-a-classic-com-component-using-wrl"></a>方法: WRL を使用して従来の COM コンポーネントを作成する

Windows ランタイム C++ テンプレートライブラリ (WRL) を使用すると、ユニバーサル Windows プラットフォーム (UWP) アプリに使用するだけでなく、デスクトップアプリで使用する基本的なクラシック COM コンポーネントを作成できます。 COM コンポーネントを作成する場合、Windows ランタイム C++ テンプレートライブラリでは ATL よりも少ないコードが必要になることがあります。 Windows ランタイム C++ テンプレートライブラリでサポートされている COM のサブセットの詳細については、「 [Windows ランタイム C++ テンプレートライブラリ (WRL)](windows-runtime-cpp-template-library-wrl.md)」を参照してください。

このドキュメントでは、Windows ランタイム C++ テンプレートライブラリを使用して、基本的な COM コンポーネントを作成する方法について説明します。 ニーズに最適な配置メカニズムを使用できますが、このドキュメントでは、デスクトップ アプリから COM コンポーネントを登録して使用する基本的な方法についても説明します。

### <a name="to-use-the-windows-runtime-c-template-library-to-create-a-basic-classic-com-component"></a>Windows ランタイム C++ テンプレートライブラリを使用して基本的なクラシック COM コンポーネントを作成するには

1. Visual Studio で、空の **ソリューション** プロジェクトを作成します。 プロジェクトにという名前を指定します。たとえば、のように指定 `WRLClassicCOM` します。

2. ソリューションに **Win32 プロジェクト** を追加します。 プロジェクトにという名前を指定します。たとえば、のように指定 `CalculatorComponent` します。 [ **アプリケーションの設定** ] タブで、[ **DLL**] を選択します。

3. **Midl ファイル (.idl)** ファイルをプロジェクトに追加します。 ファイルにという名前を指定します。たとえば、のように指定 `CalculatorComponent.idl` します。

4. CalculatorComponent.idl に次のコードを追加します。

   [!code-cpp[wrl-classic-com-component#1](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_1.idl)]

5. CalculatorComponent.cpp で、`CalculatorComponent` クラスを定義します。 クラスは、 `CalculatorComponent` [Microsoft:: wrl:: RuntimeClass](runtimeclass-class.md)から継承されます。 [Microsoft:: WRL:: RuntimeClassFlags \<ClassicCom> ](runtimeclassflags-structure.md)クラスが[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)から派生し、 [IInspectable](/windows/win32/api/inspectable/nn-inspectable-iinspectable)ではないことを指定します。 ( `IInspectable` はアプリコンポーネントを Windows ランタイムする場合にのみ使用できます)。 `CoCreatableClass` [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)などの関数で使用できるクラスのファクトリを作成します。

   [!code-cpp[wrl-classic-com-component#2](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_2.cpp)]

6. のコードを置き換えるには、次のコードを使用し `dllmain.cpp` ます。 このファイルで DLL のエクスポート関数が定義されます。 これらの関数は、 [Microsoft:: WRL:: module](module-class.md) クラスを使用して、モジュールのクラスファクトリを管理します。

   [!code-cpp[wrl-classic-com-component#3](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_3.cpp)]

7. **モジュール定義ファイル (.def)** ファイルをプロジェクトに追加します。 ファイルにという名前を指定します。たとえば、のように指定 `CalculatorComponent.def` します。 このファイルによって、エクスポートされる関数の名前がリンカーに設定されます。 プロジェクトの [**プロパティページ**] ダイアログを開き、[**構成プロパティ**] [リンカー入力] の下にある [  >  **Linker**  >  **Input****モジュール定義ファイル**] プロパティを DEF ファイルに設定します。

8. CalculatorComponent.def に次のコードを追加します。

    ```
    LIBRARY

    EXPORTS
        DllGetActivationFactory PRIVATE
        DllGetClassObject       PRIVATE
        DllCanUnloadNow         PRIVATE
    ```

9. リンカー行に runtimeobject.lib を追加します。 詳細については、「 [ `.Lib` リンカー入力としてのファイル](../../build/reference/dot-lib-files-as-linker-input.md)」を参照してください。

### <a name="to-consume-the-com-component-from-a-desktop-app"></a>デスクトップ アプリから COM コンポーネントを使用するには

1. Windows レジストリを使用して COM コンポーネントを登録します。 これを行うには、登録エントリファイルを作成し、という名前を入力して、 `RegScript.reg` 次のテキストを追加します。 *\<dll-path>* を DLL のパス (など) に置き換え `C:\temp\WRLClassicCOM\Debug\CalculatorComponent.dll` ます。

    ```
    Windows Registry Editor Version 5.00

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}]
    @="CalculatorComponent Class"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\InprocServer32]
    @="<dll-path>"
    "ThreadingModel"="Apartment"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\Programmable]

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\TypeLib]
    @="{9D3E6826-CB8E-4D86-8B14-89F0D7EFCD01}"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\Version]
    @="1.0"
    ```

2. RegScript .reg を実行するか、プロジェクトの **ビルド後イベント**に追加します。 詳細については、「 [ビルド前のイベント/ビルド後のコマンドラインダイアログボックス](/visualstudio/ide/reference/pre-build-event-post-build-event-command-line-dialog-box)」を参照してください。

3. **Win32 コンソールアプリケーション**プロジェクトをソリューションに追加します。 プロジェクトにという名前を指定します。たとえば、のように指定 `Calculator` します。

4. 次のコードを使用して、の内容を置き換え `Calculator.cpp` ます。

   [!code-cpp[wrl-classic-com-component#6](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_6.cpp)]

## <a name="robust-programming"></a>信頼性の高いプログラミング

このドキュメントでは、標準の COM 関数を使用して、Windows ランタイム C++ テンプレートライブラリを使用して COM コンポーネントを作成し、COM 対応のテクノロジで使用できるようにする方法を示します。 また、デスクトップアプリで [Microsoft:: WRL:: ComPtr](comptr-class.md) などの Windows ランタイム C++ テンプレートライブラリの種類を使用して、COM とその他のオブジェクトの有効期間を管理することもできます。 次のコードでは、Windows ランタイム C++ テンプレートライブラリを使用して、ポインターの有効期間を管理し `ICalculatorComponent` ます。 `CoInitializeWrapper` クラスは RAII ラッパーでの 1 つで、COM ライブラリが解放されることと、COM ライブラリの有効期間が `ComPtr` スマート ポインター オブジェクトよりも長く続くことを保証します。

[!code-cpp[wrl-classic-com-component#7](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_7.cpp)]

## <a name="see-also"></a>関連項目

[Windows ランタイム C++ テンプレート ライブラリ (WRL)](windows-runtime-cpp-template-library-wrl.md)
