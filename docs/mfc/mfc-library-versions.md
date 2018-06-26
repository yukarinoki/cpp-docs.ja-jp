---
title: MFC ライブラリのバージョン |Microsoft ドキュメント
ms.custom: ''
ms.date: 1/09/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- class libraries [MFC], building versions
- version information [MFC], MFC library
- MFC class library
- MFC class library, building
- MFC libraries
- MFC, library versions
- libraries [MFC], versions
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 92568f61bb1ea219ab3ddc96f4c4687dec157c9a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931766"
---
# <a name="mfc-library-versions"></a>MFC ライブラリのバージョン

マルチバイト文字セット (MBCS) コードだけではなく、Unicode (UTF 16LE、Windows ネイティブ文字セットとしてエンコード) をサポートするバージョン、MFC ライブラリは ANSI の 1 バイトをサポートするバージョンで使用されます。 各 MFC バージョンは、スタティック ライブラリ、または共有 DLL として使用できます。 MFC コントロールのサイズに非常に機密性、およびそれらのコントロールは必要ありませんアプリケーション用のダイアログ ボックスが含まれている小さな MFC スタティック ライブラリ バージョンもあります。 MFC ライブラリは、両方のデバッグで使用可能なし、リリース バージョンは、x86、x64、ARM プロセッサ アーキテクチャがサポートされています。 両方のアプリケーション (.exe ファイル) を作成して、MFC ライブラリのすべてのバージョンの Dll。 マネージ コードとのやり取りのコンパイルの MFC ライブラリのセットもします。 MFC 共有 Dll ライブラリ バイナリの互換性を示すためにバージョン番号が含まれます。

## <a name="automatic-linking-of-mfc-library-versions"></a>MFC ライブラリのバージョンの自動リンク

MFC ヘッダー ファイルには、ビルド環境で定義されている値に基づいてリンクは、MFC ライブラリの正しいバージョン自動的に決定します。 MFC ヘッダー ファイルは、MFC ライブラリの特定のバージョンのリンクをリンカーに指示コンパイラ ディレクティブを追加します。

たとえば、AFX です。H ヘッダー ファイルをリンカーに完全に静的な限られた静的、または共有 DLL バージョンの MFC; 内のリンクANSI/MBCS または Unicode のバージョンです。ビルド構成によっては、デバッグや量販店のバージョン:

```cpp
#ifndef _AFXDLL
    #ifdef _AFX_NO_MFC_CONTROLS_IN_DIALOGS
        #ifdef _DEBUG
            #pragma comment(lib, "afxnmcdd.lib")
        #else
            #pragma comment(lib, "afxnmcd.lib")
        #endif
        #pragma comment(linker, "/include:__afxNoMFCControlSupportInDialogs")
        #pragma comment(linker, "/include:__afxNoMFCControlContainerInDialogs")
    #endif
    #ifndef _UNICODE
        #ifdef _DEBUG
            #pragma comment(lib, "nafxcwd.lib")
        #else
            #pragma comment(lib, "nafxcw.lib")
        #endif
    #else
        #ifdef _DEBUG
            #pragma comment(lib, "uafxcwd.lib")
        #else
            #pragma comment(lib, "uafxcw.lib")
        #endif
    #endif
#else
    #ifndef _UNICODE
        #ifdef _DEBUG
            #pragma comment(lib, "mfc" _MFC_FILENAME_VER "d.lib")
            #pragma comment(lib, "mfcs" _MFC_FILENAME_VER "d.lib")
        #else
            #pragma comment(lib, "mfc" _MFC_FILENAME_VER ".lib")
            #pragma comment(lib, "mfcs" _MFC_FILENAME_VER ".lib")
        #endif
    #else
        #ifdef _DEBUG
            #pragma comment(lib, "mfc" _MFC_FILENAME_VER "ud.lib")
            #pragma comment(lib, "mfcs" _MFC_FILENAME_VER "ud.lib")
        #else
            #pragma comment(lib, "mfc" _MFC_FILENAME_VER "u.lib")
            #pragma comment(lib, "mfcs" _MFC_FILENAME_VER "u.lib")
        #endif
    #endif
#endif
```

MFC ヘッダー ファイルには、MFC ライブラリ、Win32 ライブラリ、OLE ライブラリが、OLE ライブラリのサンプルから構築された、ODBC ライブラリ、およびなどをなど、必要なすべてのライブラリでリンクするためのディレクティブも含まれます。 

## <a name="ansi-mbcs-and-unicode"></a>ANSI、MBCS、および Unicode

MFC ANSI/MBCS ライブラリのバージョンは、ASCII などの両方の 1 バイト文字セットをサポートし、Shift JIS などのマルチバイト文字セットします。 MFC の Unicode ライブラリのバージョンでは、その UTF 16LE ワイド文字のエンコードされた形式で Unicode をサポートします。 Utf-8 エンコードの Unicode のサポートは、MFC の ANSI/MBCS ライブラリのバージョンを使用します。

IDE で 1 バイト、マルチバイト、文字またはワイド文字の Unicode 文字列と文字サポートを使用する、プロジェクトの構成を設定するには、使用、**プロジェクト プロパティ**ダイアログ。 **構成プロパティ** > **全般** ページで、設定、**文字セット**プロパティを**未設定**を使用する、1 バイト文字セット。 プロパティを設定します**マルチ バイト文字セットを使用して**マルチバイト文字セットを使用するか**Unicode 文字セットを使用して**utf-16 としてエンコードされた Unicode を使用します。

MFC プロジェクト プリプロセッサ シンボルを使用して\_utf-16 ワイド文字の Unicode サポートを示すために UNICODE と\_MBCS を示すために MBCS をサポートします。 これらのオプションは、プロジェクトに相互に排他的です。

## <a name="mfc-static-library-naming-conventions"></a>MFC スタティック ライブラリの名前付け規則

MFC のスタティック ライブラリは、次の名前付け規則を使用します。 ライブラリの名前、フォームがあります。

> *u*AFX*c**d*です。LIB

小文字斜体で表示される文字がプレース ホルダーの指定子の意味は次の表に表示されます。

|指定子|値と意味|
|---------------|-------------------------|
|*u*|ANSI/MBCS (N) または Unicode (U) です。ダイアログで MFC コントロールなしのバージョンを省略します。|
|*c*|MFC コントロール (CW) のダイアログ ボックスで、または (NMCD) なしのバージョン|
|*d*|デバッグやリリース: D = デバッグです。リリースの指定子を省略します。|

次の表に表示されているすべてのライブラリが含まれるのサポートされているビルド アーキテクチャ \atlmfc\lib ディレクトリに作成済みです。

|ライブラリ|説明|
|-------------|-----------------|
|NAFXCW.LIB|MFC スタティック リンク ライブラリ、リリース バージョン|
|NAFXCWD.LIB|MFC スタティック リンク ライブラリのデバッグ バージョン|
|UAFXCW.LIB|Unicode をサポート、リリース バージョンの MFC スタティック リンク ライブラリ|
|UAFXCWD.LIB|Unicode をサポート、デバッグ バージョンの MFC スタティック リンク ライブラリ|
|AFXNMCD です。LIB|MFC ダイアログ コントロール、リリース バージョンがない場合、MFC スタティック リンク ライブラリ|
|AFXNMCDD です。LIB|MFC ダイアログ コントロール、デバッグ バージョンがない場合、MFC スタティック リンク ライブラリ|

同じ基本名と .pdb 拡張子を持つデバッガー ファイルも、スタティック ライブラリの各使用できます。

## <a name="mfc-shared-dll-naming-conventions"></a>MFC 共有 DLL の名前付け規則

MFC 共有 Dll も構造化された名前付け規則に従ってください。 これにより、DLL やライブラリを使用して、目的に応じてやすくします。

MFC Dll が*バージョン*バイナリの互換性を示す番号。 他のライブラリと、プロジェクト内での互換性を保証するためにコンパイラ ツールセットと同じバージョンを持つ MFC Dll を使用します。

|[DLL]|説明|
|---------|-----------------|
|MFC*バージョン*します。DLL|MFC DLL、ANSI または MBCS リリース バージョン|
|MFC*バージョン*U.DLL|MFC DLL、Unicode のリリース バージョン|
|MFC*バージョン*D.DLL|MFC DLL、ANSI または MBCS のデバッグ バージョン|
|MFC*バージョン*UD です。DLL|MFC DLL、Unicode のデバッグ バージョン|
|MFCM*バージョン*します。DLL|Windows フォーム コントロールと MFC DLL ANSI または MBCS リリース バージョン|
|MFCM*バージョン*U.DLL|Unicode のリリース バージョンの Windows フォーム コントロールと MFC DLL|
|MFCM*バージョン*D.DLL|Windows フォーム コントロールと MFC DLL ANSI または MBCS のデバッグ バージョン|
|MFCM*version*UD.DLL|Unicode のデバッグ バージョンの Windows フォーム コントロールと MFC DLL|

アプリケーションまたは MFC の拡張これらの共有 Dll を使用する Dll をビルドするためのインポート ライブラリは、DLL と同じ基本名はあるが .lib ファイル名拡張子です。 のコードでに小規模のスタティック ライブラリを共有 Dll を使用して、リンクも必要がありますこのライブラリの名前は MFCS*バージョン*{U} {D} .lib です。

アプリケーションや MFC 拡張 DLL からであるかどうか、MFC の共有 DLL バージョンを動的にリンクする場合、は、一致する MFC を含める必要があります*バージョン*します。DLL または MFC*バージョン*U.DLL、製品を展開するときにします。

アプリケーションと共に配布可能な Visual C Dll の一覧は、次を参照してください。 [Microsoft Visual Studio 2017 および Microsoft Visual Studio 2017 SDK (が含まれていますユーティリティおよび BuildServer ファイル) の再頒布可能コード](http://go.microsoft.com/fwlink/p/?LinkId=823098)です。

MFC の MBCS および Unicode のサポートの詳細については、次を参照してください。 [Unicode およびマルチバイト文字セット (MBCS) のサポート](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)です。

## <a name="dynamic-link-library-support"></a>ダイナミック リンク ライブラリのサポート

いずれか、静的であるか共有動的 MFC ライブラリを使用すると、MFC と非 MFC の両方の実行可能ファイルで使用できる Dll を作成します。 これら"レギュラー Dll"または"標準 MFC Dll"とも呼ばれますが、MFC 拡張 Dll のみを指定できますと区別するためで使用される MFC アプリと MFC Dll です。 MFC のスタティック ライブラリを使用してビルドされた DLL と呼ぶことが、USRDLL の古い参照は、MFC DLL プロジェクト プリプロセッサ シンボルを定義するため **\_USRDLL**です。 共有の Dll を使用、MFC DLL と呼ぶことが、AFXDLL、古い参照でプリプロセッサのシンボルを定義するので **\_AFXDLL**です。

MFC のスタティック ライブラリにリンクすることで、DLL プロジェクトを作成するときに、DLL は MFC 共有 Dll せずに展開できます。 DLL プロジェクトが MFC のインポート ライブラリにリンクするときに*バージョン*します。LIB のまたは MFC*バージョン*U.LIB、一致する、展開する必要があります MFC 共有 DLL MFC*バージョン*します。DLL または MFC*バージョン*DLL と共に U.DLL です。 詳細については、次を参照してください。 [Dll](../build/dlls-in-visual-cpp.md)です。

## <a name="see-also"></a>関連項目

[MFC の一般的なトピック](../mfc/general-mfc-topics.md)  
