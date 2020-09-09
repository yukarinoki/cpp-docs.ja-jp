---
title: '方法: ユニバーサル Windows プラットフォーム アプリで既存の C++ コードを使用する'
description: ユニバーサル Windows プラットフォームアプリで既存のコードアプリとライブラリを使用する方法。
ms.date: 09/04/2020
ms.assetid: 87e5818c-3081-42f3-a30d-3dca2cf0645c
ms.openlocfilehash: 1e946d588f1a14018ebb11a60b319c2d54658f25
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609127"
---
# <a name="how-to-use-existing-c-code-in-a-universal-windows-platform-app"></a>方法: ユニバーサル Windows プラットフォーム アプリで既存の C++ コードを使用する

ユニバーサル Windows プラットフォーム (UWP) プロジェクトで既存の C++ コードを使用するには、さまざまな方法があります。 コンポーネント拡張 (C++/CX) が有効になっている (つまり、オプションを使用して) コードを再コンパイルする必要がないいくつかの方法があり `/ZW` ます。 場合によっては、標準 C++ でコードを保持するか、一部のコードに対して従来の Win32 コンパイル環境を保持する必要があります。 それでも、適切なアーキテクチャを選択できるようになります。 UWP UI と、C#、Visual Basic、および JavaScript の呼び出し元に公開されている型を含むすべてのコードを検討してください。 このコードは、Windows アプリプロジェクトと Windows ランタイムコンポーネントプロジェクトに含まれている必要があります。 C++ (C++/CX を含む) からのみ呼び出すコードは、 `/ZW` オプションまたは標準 C++ プロジェクトでコンパイルされるプロジェクト内に配置できます。 禁止されている Api を使用しないバイナリのみのコードは、スタティックライブラリとしてリンクすることによって使用できます。 または、アプリをコンテンツとしてパッケージ化し、DLL に読み込むことができます。

UWP 環境でデスクトップ プログラムを実行できるようにする最も簡単な方法は、おそらく、デスクトップ ブリッジ テクノロジを使うことです。 これには、既存のアプリケーションをコードの変更を必要とせずに UWP アプリとしてパッケージ化するデスクトップアプリコンバーターが含まれます。 詳細については、[デスクトップ ブリッジ](/windows/uwp/porting/desktop-to-uwp-root)に関するページをご覧ください。

この記事の残りの部分では、C++ ライブラリ (Dll とスタティックライブラリ) をユニバーサル Windows プラットフォームに移植する方法について説明します。 コア C++ ロジックを複数の UWP アプリで使用できるように、コードを移植することができます。

UWP アプリは保護された環境で実行されます。 そのため、プラットフォームのセキュリティを損なう可能性がある多くの Win32、COM、および CRT API の呼び出しは許可されていません。 `/ZW`コンパイラオプションは、このような呼び出しを検出し、エラーを生成することができます。 アプリケーションでアプリ認定キットを使用すると、許可されていない Api を呼び出すコードを検出できます。 詳細については、「[Windows アプリ認定キット](/windows/uwp/debug-test-perf/windows-app-certification-kit)」をご覧ください。

ソースコードがライブラリで利用可能な場合は、許可されていない API 呼び出しを除去することができます。 許可されていない Api の一覧については、「[ユニバーサル Windows プラットフォームアプリでサポート](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)されていない UWP アプリと CRT 関数[の WIN32 Api と COM api](/uwp/win32-and-com/win32-and-com-for-uwp-apps) 」を参照してください。 [UWP アプリでの Windows API の代替](/uwp/win32-and-com/alternatives-to-windows-apis-uwp)に関するページで、いくつかの代替を確認できます。

ユニバーサル Windows プロジェクトから従来のデスクトップライブラリへの参照を追加しようとすると、ライブラリに互換性がないというエラーメッセージが表示されます。 スタティックライブラリの場合は、ライブラリ (ファイル) をリンカー入力に追加することでライブラリにリンクでき *`.lib`* ます。これは、従来の Win32 アプリケーションと同じです。 バイナリライブラリのみが使用可能な場合は、唯一のオプションです。 スタティックライブラリは、アプリの実行可能ファイルにリンクされます。 ただし、UWP アプリで使用する Win32 DLL は、プロジェクトに追加してコンテンツとしてマークすることによって、アプリにパッケージする必要があります。 UWP アプリで Win32 DLL を読み込むには、またはではなくを呼び出す必要もあり [`LoadPackagedLibrary`](/windows/win32/api/winbase/nf-winbase-loadpackagedlibrary) `LoadLibrary` `LoadLibraryEx` ます。

DLL またはスタティックライブラリのソースコードがある場合は、コンパイラオプションを使用して、それを UWP プロジェクトとして再コンパイルでき `/ZW` ます。 その後、 **ソリューションエクスプローラー**を使用して参照を追加し、それを C++ UWP アプリで使用できます。 エクスポートライブラリを使用して DLL をリンクします。

他の言語の呼び出し元に機能を公開するために、ライブラリを Windows ランタイム コンポーネントに変換することができます。 Windows ランタイムコンポーネントは *`.winmd`* 、.net と JavaScript のコンシューマーが必要とする方法でコンテンツを記述するファイル形式でメタデータを含むという点で、通常の dll とは異なります。  API 要素を他の言語に公開するには、ref クラスなどの C++/CX コンストラクトを追加してパブリックにすることができます。 Windows 10 以降では、c++/cxではなく、 [c++/WinRT ライブラリ](https://github.com/microsoft/cppwinrt) をお勧めします。

前の説明は COM コンポーネントには適用されません。 COM コンポーネントは、異なる方法で処理する必要があります。 EXE または DLL に COM サーバーがある場合は、ユニバーサル Windows プロジェクトで使用できます。 これを登録を必要としない [COM コンポーネント](/windows/win32/sbscs/creating-registration-free-com-objects)としてパッケージ化し、それをコンテンツファイルとしてプロジェクトに追加し、を使用してインスタンス化し [`CoCreateInstanceFromApp`](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstancefromapp) ます。 詳細については、「[Using Free-COM DLL in Windows Store C++ Project](/archive/blogs/win8devsupport/using-free-com-dll-in-windows-store-c-project)」 (Windows ストア C++ プロジェクトでの Free-COM DLL の使用) をご覧ください。

既存の COM ライブラリを UWP に移植する場合は、それを Windows ランタイムコンポーネントに変換することもできます。 このようなポートには C++/WinRT ライブラリをお勧めしますが、 [Windows ランタイム C++ テンプレートライブラリ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)を使用することもできます。 WRL は非推奨とされており、ATL および OLE のすべての機能をサポートしているわけではありません。 このようなポートが実現可能であるかどうかは、コンポーネントに必要な COM、ATL、および OLE の機能によって異なります。

どちらの開発シナリオを選択した場合でも、多くのマクロ定義に注意する必要があります。 これらのマクロをコード内で使用すると、従来のデスクトップ Win32 と UWP の両方で条件付きでコードをコンパイルできます。

```cpp
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PC_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PHONE_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_DESKTOP)
```

これらのステートメントは、それぞれ、UWP アプリ、Windows Phone ストア アプリ、両方のアプリ、どちらでもないアプリ (クラシック Win32 デスクトップのみ) の順に適用されます。 これらのマクロは Windows SDK 8.1 以降でのみ使用できます。

この記事では、次の手順について説明します。

- [UWP アプリで Win32 の DLL を使用する](#BK_Win32DLL)

- [UWP アプリでのネイティブ C++ スタティックライブラリの使用](#BK_StaticLib)

- [Windows ランタイムコンポーネントへの C++ ライブラリの移植](#BK_WinRTComponent)

## <a name="using-a-win32-dll-in-a-uwp-app"></a><a name="BK_Win32DLL"></a> UWP アプリでの Win32 DLL の使用

セキュリティと信頼性を向上させるために、ユニバーサル Windows アプリは制限付きランタイム環境で実行されます。 従来の Windows デスクトップアプリケーションでは、ネイティブ DLL を使用することはできません。 DLL のソース コードがある場合、コードが UWP 上で実行されるように、コードを移植することができます。 まず、いくつかのプロジェクト設定とプロジェクト ファイル メタデータを変更し、プロジェクトを UWP プロジェクトとして識別させます。 オプションを使用してライブラリコードを再コンパイルし `/ZW` ます。これにより、C++/cx が有効になります。 特定の API 呼び出しは、その環境に関連するより厳密な制御があるため、UWP アプリでは許可されません。 詳細については、「 [UWP アプリの Win32 api と COM api](/uwp/win32-and-com/win32-and-com-for-uwp-apps)」を参照してください。

`__declspec(dllexport)` を使用して関数をエクスポートするネイティブ DLL がある場合は、DLL を UWP プロジェクトとして再コンパイルすることで UWP アプリからこれらの関数を呼び出すことができます。 たとえば、次のヘッダーファイルのようなコードを使用して、いくつかのクラスとそのメソッドをエクスポートする *キリン* という名前の Win32 DLL プロジェクトがあるとします。

```cpp
// giraffe.h
// Define GIRAFFE_EXPORTS when building this DLL
#pragma once

#ifdef GIRAFFE_EXPORTS
#define GIRAFFE_API __declspec(dllexport)
#else
#define GIRAFFE_API
#endif

GIRAFFE_API int giraffeFunction();

class Giraffe
{
    int id;
        Giraffe(int id_in);
    friend class GiraffeFactory;

public:
    GIRAFFE_API int GetID();
};

class GiraffeFactory
{
    static int nextID;

public:
    GIRAFFE_API GiraffeFactory();
    GIRAFFE_API static int GetNextID();
    GIRAFFE_API static Giraffe* Create();
};
```

コード ファイルは以下のようになります。

```cpp
// giraffe.cpp
#include "pch.h"
#include "giraffe.h"

Giraffe::Giraffe(int id_in) : id(id_in)
{
}

int Giraffe::GetID()
{
    return id;
}

int GiraffeFactory::nextID = 0;

GiraffeFactory::GiraffeFactory()
{
    nextID = 0;
}

int GiraffeFactory::GetNextID()
{
    return nextID;
}

Giraffe* GiraffeFactory::Create()
{
    return new Giraffe(nextID++);
}

int giraffeFunction();
```

プロジェクト内の他のすべて ( *`pch.h`* 、、 *`dllmain.cpp`* ) は、標準の Win32 プロジェクトテンプレートの一部です。 このコードは、 `GIRAFFE_API` が定義されている場合にに解決されるマクロを定義し `__declspec(dllexport)` `GIRAFFE_EXPORTS` ます。 つまり、プロジェクトが DLL としてビルドされるときに定義されますが、クライアントがヘッダーを使用する場合は定義されません *`giraffe.h`* 。 この DLL は、ソースコードを変更することなく、UWP プロジェクトで使用できます。 一部のプロジェクト設定とプロパティのみを変更する必要があります。

次の手順は、を使用して関数を公開するネイティブ DLL がある場合に適用され `__declspec(dllexport)` ます。

### <a name="to-port-a-native-dll-to-the-uwp-without-creating-a-new-project"></a>新しいプロジェクトを作成せずに UWP にネイティブ DLL を移植するには

1. Visual Studio で DLL プロジェクトを開きます。

1. DLL プロジェクトの **プロジェクトプロパティ** を開き、 **構成** を [ **すべての構成**] に設定します。

1. プロジェクトの**プロパティ**の [ **C/c + +**  >  **全般**] タブで、[**使用 Windows ランタイム拡張** **] を [はい] (/ZW)** に設定します。 このプロパティは、コンポーネント拡張 (C++/CX) を有効にします。

1. **ソリューションエクスプローラー**で、プロジェクトノードを選択し、ショートカットメニューを開き、[**プロジェクトのアンロード**] をクリックします。 次に、アンロードしたプロジェクト ノードのショートカット メニューを開き、プロジェクト ファイルの編集を選択します。 `WindowsTargetPlatformVersion` 要素を検索し、次の要素に置き換えます。

    ```xml
    <AppContainerApplication>true</AppContainerApplication>
    <ApplicationType>Windows Store</ApplicationType>
    <WindowsTargetPlatformVersion>10.0.10156.0</WindowsTargetPlatformVersion>
    <WindowsTargetPlatformMinVersion>10.0.10156.0</WindowsTargetPlatformMinVersion>
    <ApplicationTypeRevision>10.0</ApplicationTypeRevision>
    ```

   *`.vcxproj`* ファイルを閉じ、ショートカットメニューを再度開き、[**プロジェクトの再読み込み**] をクリックします。

   **ソリューションエクスプローラー** によってプロジェクトがユニバーサル Windows プロジェクトとして識別されるようになりました。

1. プリコンパイル済みヘッダー ファイル名が正しいことを確認します。 プリコンパイル **済みヘッダー** のセクションで、次のようなエラーが表示された場合は、 **プリコンパイル済みヘッダーファイル** をからに変更する *`pch.h`* *`stdafx.h`* か、別の方法で変更することが必要になる場合があります。

   > エラー C2857: コマンドラインオプションで指定された ' #include ' ステートメント **`/Ycpch.h`** がソースファイルに見つかりませんでした

   問題は、古いプロジェクトテンプレートがプリコンパイル済みヘッダーファイルに対して異なる名前付け規則を使用することです。 Visual Studio 2019 以降のプロジェクトでは、を使用 *`pch.h`* します。

1. プロジェクトをビルドします。 互換性のないコマンドラインオプションに関するエラーが発生する場合があります。 たとえば、現在非推奨になっているが頻繁に使用されるオプション **[最小リビルドを有効にする (/Gm)]** は多くの古い C++ プロジェクトで既定で設定され、`/ZW` と互換性がありません。

   ユニバーサル Windows プラットフォームに対してコンパイルする場合、一部の関数は使用できません。 問題に関するコンパイラエラーが表示されます。 ビルドがクリーンになるまでこれらのエラーに対処します。

1. 同じソリューション内の uwp アプリで DLL を使用するには、uwp プロジェクトノードのショートカットメニューを開き、[参照の**追加**] を選択し  >  **Reference**ます。

   [**プロジェクト**  >  **ソリューション**] で、DLL プロジェクトの横にあるチェックボックスをオンにし、[ **OK** ] をクリックします。

1. UWP アプリのファイルにライブラリのヘッダーファイルを含め *`pch.h`* ます。

    ```cpp
    #include "..\Giraffe\giraffe.h"
    ```

1. 通常通り UWP プロジェクトにコードを追加し、関数を呼び出して、DLL から型を生成します。

    ```cpp
    MainPage::MainPage()
    {
        InitializeComponent();
        GiraffeFactory gf;
        Giraffe* g = gf.Create();
        int id = g->GetID();
    }
    ```

## <a name="using-a-native-c-static-library-in-a-uwp-app"></a><a name="BK_StaticLib"></a> UWP アプリでネイティブ C++ スタティック ライブラリを使用する

UWP プロジェクトでネイティブ C++ スタティック ライブラリを使用することはできますが、理解しておくべき制約と制限があります。 最初に [C++/CX でのスタティック ライブラリ](../cppcx/static-libraries-c-cx.md)についてご覧ください。 UWP アプリからスタティック ライブラリのネイティブ コードにアクセスすることはできますが、このようなスタティック ライブラリにパブリックな参照型を作成することは推奨されていません。 `/ZW` オプションを使用してスタティック ライブラリをコンパイルすると、ライブラリアン (実際にはリンカー) により次の警告が表示されます。

> LNK4264: は /ZW でコンパイルされたオブジェクト ファイルをスタティック ライブラリにアーカイブしています。Windows Runtime 型を作成する場合、Windows Runtime メタデータを含むスタティック ライブラリとのリンクはお勧めできません。

ただし、を使用して再コンパイルしなくても、UWP アプリでスタティックライブラリを使用でき `/ZW` ます。 ライブラリでは、ref 型を宣言したり、C++/CX コンストラクトを使用したりすることはできません。 ただし、ネイティブコードのライブラリを使用することが目的である場合は、次の手順に従って実行できます。

### <a name="to-use-a-native-c-static-library-in-a-uwp-project"></a>UWP プロジェクトでネイティブ C++ スタティック ライブラリを使用するには

1. UWP プロジェクトのプロジェクトプロパティで、左ペインの [**構成プロパティ**] [  >  **リンカー**  >  **入力**] の順に選択します。 右側のウィンドウで、**[追加の依存関係]** プロパティのライブラリにパスを追加します。 たとえば、出力をに配置するプロジェクトのライブラリの場合、 *`<SolutionFolder>\Debug\MyNativeLibrary\MyNativeLibrary.lib`* 相対パスを追加し *`Debug\MyNativeLibrary\MyNativeLibrary.lib`* ます。

1. ヘッダーファイルを参照する include ステートメントをファイルに追加するか *`pch.h`* (存在する場合)、必要に応じて任意のファイルに追加 *`.cpp`* し、ライブラリを使用するコードの追加を開始します。

   ```cpp
   #include "..\MyNativeLibrary\MyNativeLibrary.h"
   ```

   **ソリューションエクスプローラー**の [**参照設定**ノードには参照を追加しないでください。 このメカニズムは、Windows ランタイム コンポーネントの場合のみ機能します。

## <a name="porting-a-c-library-to-a-windows-runtime-component"></a><a name="BK_WinRTComponent"></a> C++ ライブラリをWindows ランタイム コンポーネントに移植する

UWP アプリからスタティックライブラリのネイティブ Api を使用するとします。 ネイティブライブラリのソースコードがある場合は、Windows ランタイムコンポーネントにコードを移植できます。 これは、スタティックライブラリではなくなります。これを、任意の C++ UWP アプリで使用できる DLL に変換します。 この手順では、C++/CX 拡張機能を使用する新しい Windows ランタイムコンポーネントを作成する方法について説明します。 代わりに C++/winrt を使用するコンポーネントを作成する方法については、「 [c++/winrt を](/windows/uwp/winrt-components/create-a-windows-runtime-component-in-cppwinrt)使用したコンポーネントの Windows ランタイム」を参照してください。

C++/CX を使用する場合、参照型およびその他の C++/CX コンストラクトを追加できます。これは、任意の UWP アプリコードでクライアントが使用できます。 C#、Visual Basic、または JavaScript からこれらの型にアクセスできます。 基本手順は次のとおりです。

- Windows ランタイムコンポーネント (ユニバーサル Windows) プロジェクトを作成します。
- スタティックライブラリのコードをコピーして、
- オプションによって発生したコンパイラのエラーに対処 `/ZW` します。

### <a name="to-port-a-c-library-to-a-windows-runtime-component"></a>C++ ライブラリを Windows ランタイム コンポーネントに移植するには

1. Windows ランタイムコンポーネント (ユニバーサル Windows) プロジェクトを作成します。

1. プロジェクトを閉じます。

1. **Windows エクスプローラー**で、新しいプロジェクトを見つけます。 次に、移植するコードを含む C++ ライブラリプロジェクトを見つけます。 C++ ライブラリプロジェクトから、ソースファイル (サブディレクトリ内のヘッダーファイル、コードファイル、その他のリソースなど) をコピーします。 新しいプロジェクトフォルダーに貼り付け、同じフォルダー構造を保持します。

1. Windows ランタイムコンポーネントプロジェクトを再度開きます。 **ソリューションエクスプローラー**でプロジェクトノードのショートカットメニューを開き、[既存項目の**追加**] を選択し  >  **Existing Item**ます。

1. 元のプロジェクトから追加するすべてのファイルを選択し、[ **OK]** を選択します。 サブフォルダーについても必要に応じてこの操作を繰り返します。

1. 一部のコードが重複している可能性があります。 プリコンパイル済みヘッダーが複数ある場合 (およびの両方 *`stdafx.h`* *`pch.h`* ) は、保持するものを1つ選択します。 include ステートメントなどの必要なコードはすべて、保持する方にコピーしておきます。 次に、もう1つを削除し、プロジェクトのプロパティの [ **プリコンパイル済みヘッダー**] で、ヘッダーファイルの名前が正しいことを確認します。

   プリコンパイル済みヘッダーとして使用するファイルを変更した場合、プリコンパイル済みヘッダー オプションが各ファイルに対して正しいことを確認します。 各 *`.cpp`* ファイルを順番に選択し、[プロパティ] ウィンドウを開いて、[**作成 (/yc)**] に設定する必要があるプリコンパイル済みヘッダーを除き、[すべて] が [**使用] (/yu)** に設定されていることを確認します。

1. プロジェクトをビルドし、エラーを解決します。 これらのエラーは、オプションを使用した場合 `/ZW` 、または新しいバージョンの Windows SDK が原因で発生した可能性があります。 また、ライブラリが依存するヘッダーファイルなどの依存関係や、古いプロジェクトと新しいプロジェクトの間のプロジェクト設定の違いが反映されている場合もあります。

1. パブリック参照型をプロジェクトに追加するか、通常の型を参照型に変換します。 これらの型を使用して、UWP アプリから呼び出す機能にエントリポイントを公開します。

1. UWP アプリ プロジェクトからコンポーネントへの参照を追加してコンポーネントをテストし、作成したパブリック API を呼び出すコードを追加します。

## <a name="see-also"></a>関連項目

[ユニバーサル Windows プラットフォームへの移植](../porting/porting-to-the-universal-windows-platform-cpp.md)
