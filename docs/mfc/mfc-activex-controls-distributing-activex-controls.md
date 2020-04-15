---
title: 'MFC ActiveX コントロール : ActiveX コントロールの配布'
ms.date: 09/12/2018
f1_keywords:
- GetWindowsDirectory
- GetSystemDirectory
helpviewer_keywords:
- MFC ActiveX controls [MFC], ANSI or Unicode versions
- RegSvr32.exe
- MFC ActiveX controls [MFC], distributing
- distributing MFC ActiveX controls
- redistributable files, MFC ActiveX controls
- GetSystemDirectory method [MFC]
- registering ActiveX controls
- MSVCRT40.dll
- registry [MFC], registering controls
- LoadLibrary method, registering ActiveX controls
- MFC40U.DLL
- MFC40.DLL
- GetWindowsDirectory method [MFC]
- installing ActiveX controls
- GetProcAddress method, registering ActiveX controls
- MFC ActiveX controls [MFC], installing
- MFC ActiveX controls [MFC], registering
- registering controls
- OLEPRO32.DLL
ms.assetid: cd70ac9b-f613-4879-9e81-6381fdfda2a1
ms.openlocfilehash: 1ada1c801b2d9d62f1cc4cd5bf72a2995225b3de
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364623"
---
# <a name="mfc-activex-controls-distributing-activex-controls"></a>MFC ActiveX コントロール : ActiveX コントロールの配布

この資料では、ActiveX コントロールの再配布に関連するいくつかの問題について説明します。

- [ANSI またはユニコード コントロールのバージョン](#_core_ansi_or_unicode_control_versions)

- [ActiveX コントロールと再頒布可能 DLL のインストール](#_core_installing_activex_controls_and_redistributable_dlls)

- [コントロールの登録](#_core_registering_controls)

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX に取って代わる最新テクノロジの詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

## <a name="ansi-or-unicode-control-versions"></a><a name="_core_ansi_or_unicode_control_versions"></a>ANSI またはユニコード コントロールのバージョン

ANSI バージョンと Unicode バージョンのコントロールのどちらを出荷するか、またはその両方を出荷するかを決定する必要があります。 この決定は、ANSI および Unicode 文字セットに固有の移植性要因に基づいています。

すべての Win32 オペレーティング システムで動作する ANSI コントロールにより、さまざまな Win32 オペレーティング システム間で最大の移植性を実現できます。 Unicode コントロールは Windows NT (バージョン 3.51 以降) でのみ動作しますが、Windows 95 または Windows 98 では動作しません。 携帯性が主な関心事である場合は、ANSI コントロールを出荷してください。 コントロールが Windows NT でのみ実行される場合は、Unicode コントロールを出荷できます。 両方を出荷し、アプリケーションにユーザーのオペレーティング システムに最適なバージョンをインストールすることもできます。

## <a name="installing-activex-controls-and-redistributable-dlls"></a><a name="_core_installing_activex_controls_and_redistributable_dlls"></a>ActiveX コントロールと再頒布可能 DLL のインストール

ActiveX コントロールに付属のセットアップ プログラムは、Windows ディレクトリの特別なサブディレクトリを作成し、コントロールをインストールする必要があります。OCX ファイルが含まれています。

> [!NOTE]
> セットアップ プログラム`GetWindowsDirectory`で Windows API を使用して、Windows ディレクトリの名前を取得します。 会社名や製品名からサブディレクトリ名を取得することもできます。

セットアップ プログラムは、必要な再頒布可能 DLL ファイルを Windows システム ディレクトリにインストールする必要があります。 ユーザーのコンピュータに既に DLL が存在する場合は、セットアップ プログラムで、そのバージョンとインストールするバージョンを比較する必要があります。 ファイルのバージョン番号が既にインストールされているファイルよりも大きい場合にのみ、ファイルを再インストールします。

ActiveX コントロールは OLE コンテナー アプリケーションでのみ使用できるため、コントロールと共に OLE DLL の完全なセットを配布する必要はありません。 含まれているアプリケーション (またはオペレーティング システム自体) に、標準の OLE DLL がインストールされていると仮定できます。

## <a name="registering-controls"></a><a name="_core_registering_controls"></a>コントロールの登録

コントロールを使用する前に、Windows 登録データベースに適切なエントリを作成する必要があります。 ActiveX コントロール コンテナーには、ユーザーが新しいコントロールを登録するためのメニュー項目が用意されているものもありますが、この機能は、すべてのコンテナーで使用できるとはいえません。 したがって、セットアップ プログラムでコントロールをインストールするときに登録する必要があります。

必要に応じて、コントロールを直接登録するセットアップ プログラムを記述できます。

Windows `LoadLibrary` API を使用して、コントロール DLL を読み込みます。 次に、"DllRegisterServer" 関数のアドレスを取得するために使用`GetProcAddress`します。 最後に、関数`DllRegisterServer`を呼び出します。 次のコード サンプルは、コントロール ライブラリの`hLib`ハンドルを格納し`lpDllEntryPoint`、"DllRegisterServer" 関数のアドレスを格納する、考えられる 1 つのメソッドを示しています。

[!code-cpp[NVC_MFC_AxCont#16](../mfc/codesnippet/cpp/mfc-activex-controls-distributing-activex-controls_1.cpp)]

コントロールを直接登録する利点は、別のプロセス (REGSVR32) を呼び出してロードする必要がなくなるため、インストール時間が短縮されます。 また、登録は内部プロセスであるため、セットアップ プログラムは外部プロセスよりもエラーや予期しない状況に対処できます。

> [!NOTE]
> セットアップ プログラムが ActiveX コントロールをインストールする前に`OleInitialize`、 を呼び出す必要があります。 セットアップ プログラムが終了したら、`OleUnitialize`に電話します。 これにより、OLE システム DLL が ActiveX コントロールを登録するための適切な状態になります。

MFCx0.DLL を登録する必要があります。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)
