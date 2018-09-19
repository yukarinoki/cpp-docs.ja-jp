---
title: DLL と実行可能ファイルのリンク |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- run time [C++], linking
- dynamic load linking [C++]
- linking [C++], DLLs
- DLLs [C++], linking
- implicit linking [C++]
- explicit linking [C++]
- executable files [C++], linking to DLLs
- loading DLLs [C++]
ms.assetid: 7592e276-dd6e-4a74-90c8-e1ee35598ea3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a0781a2257197314b75ae46ec2557d0b698cb9a7
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702015"
---
# <a name="link-an-executable-to-a-dll"></a>DLL と実行形式のリンク

実行可能ファイルを DLL とリンクするには、次の 2 つの方法があります。

- *暗黙的リンク*オペレーティング システムに DLL が読み込まれて使用する実行可能ファイルが読み込まれるときに位置します。 クライアント実行可能ファイルは、場合と同様、関数の表示に、実行可能ファイル内に含まれるが静的にリンクに、DLL のエクスポートされた関数を呼び出します。 暗黙的リンクとも呼ば*静的読み込み*または*負荷時の動的リンク*します。

- *明示的リンク*、オペレーティング システムが実行時にオンデマンドで DLL を読み込みます。 明示的なリンクすることで、DLL を使用する実行可能ファイルには、明示的に読み込むし、DLL をアンロードして、DLL によってエクスポートされた関数にアクセスする関数呼び出しを行う必要があります。 静的にリンクされたライブラリ内の関数を呼び出しとは異なり、クライアント実行可能ファイルは関数ポインターを通じて DLL のエクスポートされた関数を呼び出す必要があります。 明示的なリンクが呼ば*動的な負荷*または*実行時の動的リンク*します。

実行可能ファイルは、同じ DLL にリンクするリンクのいずれかの方法を使用できます。 さらに、これらのメソッドは相互に排他的です。1 つの実行可能ファイルは、DLL を暗黙的にリンクでき、明示的にアタッチできます別します。

<a name="determining-which-linking-method-to-use"></a>

## <a name="determine-which-linking-method-to-use"></a>リンク方式の使い分け

暗黙的なリンクまたは明示的なリンクを使用するかどうかは、アーキテクチャの決定、アプリケーションに対して行う必要があります。 各メソッドに長所と短所があります。

### <a name="implicit-linking"></a>暗黙的リンク

暗黙的リンクは、アプリケーションのコードは、エクスポートされた DLL 関数を呼び出すときに発生します。 DLL 関数を呼び出す実行形式のソース コードをコンパイルまたはアセンブルすると、オブジェクト コード内に外部関数への参照が生成されます。 この外部参照を解決するには、アプリケーションをインポート ライブラリ (.lib) ファイルとリンクする必要があります。インポート ライブラリは、DLL の作成元が提供します。

インポート ライブラリには、DLL を読み込んで、DLL 内の関数呼び出しを実装するコードが含まれるだけです。 リンカーは、インポート ライブラリ内に外部関数を見つけると、その関数のコードは DLL 内にあるものと認識します。 リンカーは、単に DLL コードの場所を実行可能ファイルに記入することによって、外部参照を解決します。システムはプロセスの起動時にこの情報を利用します。

動的にリンクされた参照を含むプログラムが起動されると、プログラムの実行可能ファイル内の情報に従って、必要な DLL を探します。 DLL が見つからないと、システムは処理を停止し、ダイアログ ボックスを表示して、エラーを報告します。 見つかった場合は、DLL モジュールがプロセスのアドレス空間に割り当てられます。

などの初期化と終了のコードをエントリ ポイント関数があります Dll の場合`DllMain`、オペレーティング システム、関数を呼び出します。 エントリ ポイント関数に渡されるパラメーターの 1 つは、DLL がプロセスにアタッチされようとしていることを示すコードになります。 エントリ ポイント関数が TRUE を返さない場合、システムは処理を停止し、エラーを報告します。

最後に、システムはプロセスの実行可能コードを変更し、その DLL 関数の開始アドレスをセットします。

プログラム コードの残りの部分と同じように、DLL コードはプロセスの開始時にプロセスのアドレス空間に割り当てられますが、メモリに読み込まれるのはそれが必要とされたときです。 結果として、`PRELOAD`と`LOADONCALL`不要になった以前のバージョンの Windows で読み込みを制御する .def ファイルで使用されるコードの属性が意味を持ちます。

### <a name="explicit-linking"></a>明示的リンク

暗黙的リンクは最も使いやすい方法なので、多くのアプリケーションは、暗黙的リンクを使います。 ただし、明示的なリンクが必要な場合もあります。 ここでは、明示的リンクを使う一般的な理由について説明します。

- アプリケーションでは、実行時まで読み込まれる DLL の名前は知りません。 たとえば、アプリケーションでは、起動時の構成ファイルから、DLL と、エクスポートされた関数の名前を取得する可能性があります。

- プロセスの起動時に、DLL が見つからない場合、暗黙的なリンクを使用するプロセスは、オペレーティング システムによって終了します。 明示的リンクを使用するプロセスはこのような状況では、終了していないと、エラーから回復を試みることができます。 たとえば、プロセスがユーザーにエラーを通知して、ユーザーに DLL への別のパスを指定させることができます。

- それにリンクする Dll の場合にも、暗黙的なリンクを使用するプロセスが終了する`DllMain`関数が失敗します。 明示的リンクを使用するプロセスは、このような状況で終端がありません。

- Windows は、アプリケーションの読み込み時にすべての DLL を読み込むため、暗黙的に多くの DLL とリンクするアプリケーションは、起動に時間がかかることがあります。 起動時のパフォーマンスを向上させるには、アプリケーションにリンクして暗黙的に読み込み、および待機の直後後に明示的にリンクするその他の Dll が必要になるまでに必要なそれらの Dll にのみ

- 明示的リンク、インポート ライブラリを使用してアプリケーションをリンクする必要はありません。 DLL 内の変更、エクスポート序数を変更する場合、明示的リンクを使用するアプリケーションを呼び出す場合に再リンクするにはありません`GetProcAddress`序数値ではなく、関数の名前を使用して暗黙的なリンクを使用するアプリケーションとリンクし直す必要がありますが、新しいインポート ライブラリ。

明示的リンクの欠点は、次の 2 つです。

- DLL がある場合、`DllMain`エントリ ポイント関数では、オペレーティング システム関数を呼び出したスレッドのコンテキストで`LoadLibrary`します。 以前の呼び出しのため、プロセスに DLL が既にアタッチされている場合、エントリ ポイント関数は呼び出されません`LoadLibrary`いるかどうかに対応する呼び出し、`FreeLibrary`関数。 DLL で使用する場合、明示的なリンクと、問題が発生することができます、`DllMain`関数のスレッドが既に存在するために、プロセスの各スレッドの初期化を実行するときに`LoadLibrary`(または`AfxLoadLibrary`) と呼びますが初期化されていません。

- DLL が静的範囲としてのデータを宣言する場合`__declspec(thread)`、明示的にリンクされている場合に保護エラーが発生できます。 呼び出して、DLL が読み込まれた後`LoadLibrary`コードは、このデータを参照するたびに保護違反が発生します。 静的範囲のデータには、グローバル スタティック アイテムとローカル スタティック アイテムの両方が含まれます。そのため、DLL を作成するときにする必要がありますか、スレッド ローカル ストレージを使用しないようにまたは DLL の動的な読み込みの潜在的な落とし穴について DLL のユーザーに通知。 詳細については、次を参照してください。[ダイナミック リンク ライブラリ (Windows SDK) でスレッド ローカル ストレージを使用して](/windows/desktop/Dlls/using-thread-local-storage-in-a-dynamic-link-library)します。

<a name="linking-implicitly"></a>

## <a name="how-to-link-implicitly-to-a-dll"></a>DLL と暗黙的にリンクする方法

暗黙的なリンクすることで、DLL を使用するには、クライアント実行可能ファイルは、DLL のプロバイダーからこれらのファイルを取得する必要があります。

- 1 つまたは複数ヘッダー ファイル (.h ファイル)、エクスポートされたデータ、関数、および DLL の C++ クラスの宣言が含まれています。 クラス、関数、および DLL によってエクスポートされたデータすべて設定されなければなりません`__declspec(dllimport)`ヘッダー ファイル。 詳細については、次を参照してください。 [dllexport、dllimport](../cpp/dllexport-dllimport.md)します。

- 実行可能ファイルにリンクするインポート ライブラリ。 リンカーは、DLL のビルド時に、インポート ライブラリを作成します。 詳細については、次を参照してください。[します。LIB ファイル](../build/reference/dot-lib-files-as-linker-input.md)します。

- 実際の DLL ファイル。

暗黙的なリンクすることで、DLL を使用するには、実行可能ファイルは、データ、関数、またはエクスポートされたデータ、関数、およびクラスへの呼び出しを含む各ソース ファイル内の DLL によってエクスポートされた C++ クラスを宣言するヘッダー ファイルを含める必要があります。 コーディングの観点から、エクスポートされた関数の呼び出しは、その他の関数呼び出しと同じようには。

実行可能ファイルの呼び出しをビルドするには、インポート ライブラリとリンクする必要があります。 外部メイクファイルを使用するか、またはシステムを構築する場合は、その他のオブジェクト (.obj) ファイルを一覧表示、インポート ライブラリまたはリンクするライブラリのファイル名を指定します。

オペレーティング システムは、呼び出し実行形式の読み込み時に、DLL ファイルを配置できる必要があります。 つまり、アプリケーションがデプロイまたはアプリケーションがインストールされている場合に、DLL の存在を確認する必要があります。

<a name="linking-explicitly"></a>

## <a name="how-to-link-explicitly-to-a-dll"></a>DLL を明示的にリンクする方法

DLL を使用して、明示的なリンクすることによって、アプリケーションは関数を明示的に実行時に、DLL を読み込む呼び出しを行う必要があります。 DLL と明示的にリンクするには、アプリケーションは、以下の手順を実行します。

- 呼び出す[LoadLibrary](loadlibrary-and-afxloadlibrary.md)、 `LoadLibraryEx`、または同様の機能を DLL を読み込むし、モジュール ハンドルを取得します。

- 呼び出す[GetProcAddress](getprocaddress.md)それぞれに関数ポインターを取得するアプリケーションが呼び出す関数をエクスポートします。 アプリケーションは、ポインターを通じて DLL 関数を呼び出すため、コンパイラがインポート ライブラリとリンクする必要がない外部参照を生成していません。 ただし、必要な`typedef`または`using`呼び出すエクスポートされた関数の呼び出しシグネチャを定義するステートメント。

- 呼び出す[FreeLibrary](freelibrary-and-afxfreelibrary.md) DLL の終了時にします。

たとえば、この関数のサンプルが呼び出す`LoadLibrary`"MyDLL"という名前の DLL を読み込むには、呼び出す`GetProcAddress`"DLLFunc1"という名前の関数へのポインターを取得する関数を呼び出すと、結果を保存およびを呼び出して`FreeLibrary`DLL をアンロードします。

```C
#include "windows.h"

typedef HRESULT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT*);

HRESULT LoadAndCallSomeFunction(DWORD dwParam1, UINT * puParam2)
{
    HINSTANCE hDLL;               // Handle to DLL
    LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer
    HRESULT hrReturnVal;

    hDLL = LoadLibrary("MyDLL");
    if (NULL != hDLL)
    {
        lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL, "DLLFunc1");
        if (NULL != lpfnDllFunc1)
        {
            // call the function
            hrReturnVal = lpfnDllFunc1(dwParam1, puParam2);
        }
        else
        {
            // report the error
            hrReturnVal = ERROR_DELAY_LOAD_FAILED;
        }
        FreeLibrary(hDLL);
    }
    else
    {
        hrReturnVal = ERROR_DELAY_LOAD_FAILED;
    }
    return hrReturnVal;
}
```

異なり、この例ではほとんどの場合を呼び出す必要があります`LoadLibrary`と`FreeLibrary`する DLL の複数の関数を呼び出すか、DLL を呼び出す場合に特に指定の DLL をアプリケーションで 1 回だけが繰り返し関数。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [インポート ライブラリとエクスポート ファイル](../build/reference/working-with-import-libraries-and-export-files.md)

- [ダイナミック リンク ライブラリの検索順序](/windows/desktop/Dlls/dynamic-link-library-search-order)

## <a name="see-also"></a>関連項目

[Visual C++ の DLL](../build/dlls-in-visual-cpp.md)