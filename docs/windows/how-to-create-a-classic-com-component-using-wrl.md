---
title: '方法: WRL を使用して従来の COM コンポーネントを作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 5efe7690-90d5-4c3c-9e53-11a14cefcb19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 00f00b265128ca388a3e9d4eb77631a320fbda81
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880086"
---
# <a name="how-to-create-a-classic-com-component-using-wrl"></a>方法: WRL を使用して従来の COM コンポーネントを作成する
Windows ランタイム C++ テンプレート ライブラリ (WRL) を使用すると、ユニバーサル Windows プラットフォーム (UWP) アプリを使用することだけでなく、デスクトップ アプリで使用するための基本的な従来の COM コンポーネントを作成します。 Windows ランタイム C++ テンプレート ライブラリの COM コンポーネントの作成、ATL よりも少ないコードを必要があります。 Windows ランタイム C++ テンプレート ライブラリをサポートする COM のサブセットについては、次を参照してください。 [Windows ランタイム C++ テンプレート ライブラリ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)です。  
  
 このドキュメントでは、Windows ランタイム C++ テンプレート ライブラリを使用して基本的な COM コンポーネントを作成する方法を示します。 ニーズに最適な配置メカニズムを使用できますが、このドキュメントでは、デスクトップ アプリから COM コンポーネントを登録して使用する基本的な方法についても説明します。  
  
### <a name="to-use-the-windows-runtime-c-template-library-to-create-a-basic-classic-com-component"></a>Windows ランタイム C++ テンプレート ライブラリを使用して基本のクラシック COM コンポーネントを作成するには  
  
1.  Visual Studio で、作成、**空のソリューション**プロジェクト。 など、プロジェクトの名前`WRLClassicCOM`です。  
  
2.  追加、 **Win32 プロジェクト**をソリューションにします。 など、プロジェクトの名前`CalculatorComponent`です。 **アプリケーション設定**] タブで [ **DLL**です。  
  
3.  追加、 **Midl ファイル (.idl)** ファイルをプロジェクト。 など、ファイルの名前`CalculatorComponent.idl`です。  
  
4.  CalculatorComponent.idl に次のコードを追加します。  
  
     [!code-cpp[wrl-classic-com-component#1](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_1.idl)]  
  
5.  CalculatorComponent.cpp で、`CalculatorComponent` クラスを定義します。 `CalculatorComponent`クラスから継承[Microsoft::WRL::RuntimeClass](../windows/runtimeclass-class.md)です。 [Microsoft::WRL::RuntimeClassFlags\<ClassicCom >](../windows/runtimeclassflags-structure.md)クラスの派生元を示す[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509\(v=vs.85\).aspx)および not [IInspectable](http://msdn.microsoft.com/library/br205821\(v=vs.85\).aspx)です。 (`IInspectable`は Windows ランタイム アプリのコンポーネントでのみ使用できます)。`CoCreatableClass`など関数と共に使用することができます、クラスのファクトリを作成[CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615\(v=vs.85\).aspx)です。  
  
     [!code-cpp[wrl-classic-com-component#2](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_2.cpp)]  
  
6.  次のコードを使用して、dllmain.cpp のコードを置き換えます。 このファイルで DLL のエクスポート関数が定義されます。 これらの関数を使用して、 [Microsoft::WRL::Module](../windows/module-class.md)モジュールのクラス ファクトリを管理するクラス。  
  
     [!code-cpp[wrl-classic-com-component#3](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_3.cpp)]  
  
7.  追加、**モジュール定義ファイル (.def)** ファイルをプロジェクト。 など、ファイルの名前`CalculatorComponent.def`です。 このファイルによって、エクスポートされる関数の名前がリンカーに設定されます。  
  
8.  CalculatorComponent.def に次のコードを追加します。  
  
    ```
    LIBRARY

    EXPORTS
        DllGetActivationFactory PRIVATE
        DllGetClassObject       PRIVATE
        DllCanUnloadNow         PRIVATE  
    ```

9. リンカー行に runtimeobject.lib を追加します。 学習する方法についてを参照してください[です。ファイルをリンカー入力として lib](../build/reference/dot-lib-files-as-linker-input.md)です。  
  
### <a name="to-consume-the-com-component-from-a-desktop-app"></a>デスクトップ アプリから COM コンポーネントを使用するには  
  
1.  Windows レジストリを使用して COM コンポーネントを登録します。 これを行うには、登録エントリ ファイルを作成、名前を付けます`RegScript.reg`、し、次のテキストを追加します。 置換 *\<dll パス >* 、DLL のパスを持つ — たとえば、`C:\\temp\\WRLClassicCOM\\Debug\\CalculatorComponent.dll`です。  
  
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
  
2.  RegScript.reg を実行するかに、プロジェクトの追加**ビルド後イベント**です。 詳細については、次を参照してください。[ビルド前のビルド後イベント コマンド ライン ダイアログ ボックス](/visualstudio/ide/reference/pre-build-event-post-build-event-command-line-dialog-box)です。  
  
3.  追加、 **Win32 コンソール アプリケーション**プロジェクトがソリューションにします。 など、プロジェクトの名前`Calculator`です。  
  
4.  次のコードを使用して Calculator.cpp の内容を置き換えます。  
  
     [!code-cpp[wrl-classic-com-component#6](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_6.cpp)]  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 このドキュメントでは、標準の COM 関数を使用して、COM コンポーネントを作成および COM 対応テクノロジを使用できるようにする Windows ランタイム C++ テンプレート ライブラリを使用することができますを示します。 など、Windows ランタイム C++ テンプレート ライブラリの型を使用することもできます。 [Microsoft::WRL::ComPtr](../windows/comptr-class.md) COM や他のオブジェクトの有効期間を管理するデスクトップ アプリでします。 次のコードの有効期間を管理する Windows ランタイム C++ テンプレート ライブラリを使用して、`ICalculatorComponent`ポインター。 `CoInitializeWrapper` クラスは RAII ラッパーでの 1 つで、COM ライブラリが解放されることと、COM ライブラリの有効期間が `ComPtr` スマート ポインター オブジェクトよりも長く続くことを保証します。  
  
 [!code-cpp[wrl-classic-com-component#7](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_7.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [Windows ランタイム C++ テンプレート ライブラリ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)