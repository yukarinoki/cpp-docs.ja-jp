---
description: '詳細情報: MFC に静的にリンクされた標準 MFC DLL'
title: MFC に静的にリンクされた標準 MFC DLL
ms.date: 11/04/2016
helpviewer_keywords:
- regular MFC DLLs [C++]
- DLLs [C++], regular
- USRDLLs
- USRDLLs, statically linked to MFC
- statically linked DLLs [C++]
- regular MFC DLLs [C++], statically linked to MFC
ms.assetid: 2eed531c-726a-4b8a-b936-f721dc00a7fa
ms.openlocfilehash: b213be6bf076557fc57a5bcac62cbf9767587bd3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273801"
---
# <a name="regular-mfc-dlls-statically-linked-to-mfc"></a>MFC に静的にリンクされた標準 MFC DLL

MFC に静的にリンクされた標準 MFC DLL は、MFC を内部で使用する DLL であり、その DLL 内のエクスポートされた関数は、MFC または非 MFC 実行可能ファイルから呼び出すことができます。 名前が示すように、この種類の DLL は、MFC の静的リンク ライブラリ バージョンを使用してビルドされます。 通常、関数は標準の C インターフェイスを使用して標準 MFC DLL からエクスポートされます。 標準 MFC DLL を記述、ビルド、および使用する方法の例については、サンプルの [DLLScreenCap](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/DllScreenCap) を参照してください。

USRDLL という用語は、Visual C++ ドキュメントでは使用されなくなったので注意してください。 MFC に静的にリンクされた標準 MFC DLL は、旧 USRDLL と特性が同じです。

MFC に静的にリンクされた標準 MFC DLL には、次の特徴があります。

- クライアント実行可能ファイルは、DLL (C、C++、Pascal、Visual Basic など) の使用をサポートする任意の言語で記述できます。MFC アプリケーションである必要はありません。

- DLL は、アプリケーションで使用されるのと同じ MFC 静的リンク ライブラリにリンクできます。 DLL 用の独立したバージョンの静的リンク ライブラリはなくなりました。

- MFC のバージョン 4.0 より前は、USRDLL により、MFC に静的にリンクされた標準 MFC DLL と同じ種類の機能が提供されていました。 Visual C++ バージョン 4.0 で、USRDLL という用語は廃止されました。

MFC に静的にリンクされた標準 MFC DLL には、次の要件があります。

- この種類の DLL は、`CWinApp` から派生したクラスをインスタンス化する必要があります。

- この種類の DLL では、MFC から提供される `DllMain` を使用します。 通常の MFC アプリケーションと同様に、すべての DLL 固有の初期化コードを `InitInstance` メンバー関数内に配置し、終了コードを `ExitInstance` 内に配置します。

- USRDLL という用語は廃止されましたが、コンパイラのコマンド ラインで " **_USRDLL**" を定義する必要があります。 この定義で、MFC ヘッダー ファイルからどの宣言を取り込むかを決定します。

標準 MFC DLL には、MFC アプリケーションと同様に、`CWinApp` 派生クラスと、そのアプリケーション クラスの 1 つのオブジェクトが必要です。 ただし、DLL の `CWinApp` オブジェクトは、アプリケーションの `CWinApp` オブジェクトとは異なり、メイン メッセージ ポンプはありません。

アプリケーションにはメイン メッセージ ポンプがあるため、`CWinApp::Run` メカニズムは DLL に適用されないことに注意してください。 DLL がモードレス ダイアログを開く場合、または独自のメイン フレーム ウィンドウがある場合、アプリケーションのメイン メッセージ ポンプは、DLL によってエクスポートされたルーチンを呼び出し、次に DLL のアプリケーション オブジェクトの `CWinApp::PreTranslateMessage` メンバー関数を呼び出す必要があります。

この関数の例については、DLLScreenCap サンプルを参照してください。

通常、シンボルは標準の C インターフェイスを使用して標準 MFC DLL からエクスポートされます。 標準 MFC DLL からエクスポートされた関数の宣言は、次のようになります。

```
extern "C" __declspec(dllexport) MyExportedFunction( );
```

標準 MFC DLL 内のメモリ割り当てはすべて、その DLL 内に存在する必要があります。DLL は、呼び出し実行可能ファイルに次のいずれかを渡しても、受け取ってもいけません。

- MFC オブジェクトへのポインター

- MFC によって割り当てられたメモリへのポインター

上記のいずれかを実行する必要がある場合、または呼び出し実行可能ファイルと DLL との間で MFC 派生オブジェクトを受け渡す必要がある場合は、MFC 拡張 DLL をビルドする必要があります。

データのコピーを作成する場合のみ、アプリケーションと DLL の間で C ランタイム ライブラリによって割り当てられたメモリへのポインターを渡しても安全です。 これらのポインターは、削除またはサイズ変更しないでください。メモリのコピーを作成せずに使用することもしないでください。

MFC に静的にリンクされている DLL は、共有 MFC DLL に動的にリンクすることもできません。 MFC に静的にリンクされた DLL は、他の DLL と同様に、アプリケーションに動的にバインドされます。アプリケーションは、他の DLL と同様に、その DLL にリンクします。

標準 MFC 静的リンク ライブラリには、[MFC DLL の名前付け規則](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)に説明されている規則に従って名前が付けられます。 ただし、MFC バージョン 3.0 以降では、リンク先の MFC ライブラリのバージョンをリンカーに手動で指定する必要がなくなりました。 代わりに、MFC ヘッダー ファイルにより、プリプロセッサの定義 ( **\_DEBUG** や **_UNICODE** など) に基づいて、リンク先の MFC ライブラリの正しいバージョンが自動的に決定します。 MFC ヘッダー ファイにより、MFC ライブラリの特定のバージョンでリンクするようにリンカーに指示する /DEFAULTLIB ディレクティブが追加されます。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [標準 MFC DLL の初期化](run-time-library-behavior.md#initializing-regular-dlls)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [DLL の構成要素としての MFC](../mfc/tn011-using-mfc-as-part-of-a-dll.md)

- [レギュラー MFC DLL でのデータベース、OLE、およびソケット MFC 拡張 DLL の使用](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

- [MFC DLL の作成](../mfc/reference/mfc-dll-wizard.md)

- [MFC と動的にリンクされるレギュラー MFC DLL](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC 拡張 DLL](extension-dlls-overview.md)

## <a name="see-also"></a>関連項目

[DLL の種類](kinds-of-dlls.md)
