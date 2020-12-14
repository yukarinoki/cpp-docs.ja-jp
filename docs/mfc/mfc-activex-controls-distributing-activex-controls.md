---
description: '詳細については、「MFC ActiveX コントロール: ActiveX コントロールの配布」を参照してください。'
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
ms.openlocfilehash: faf85bffd9911c38764aea19d1ddb682fd719be1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280717"
---
# <a name="mfc-activex-controls-distributing-activex-controls"></a>MFC ActiveX コントロール : ActiveX コントロールの配布

この記事では、ActiveX コントロールの再頒布に関連するいくつかの問題について説明します。

- [ANSI または Unicode のコントロールバージョン](#_core_ansi_or_unicode_control_versions)

- [ActiveX コントロールと再頒布可能 Dll のインストール](#_core_installing_activex_controls_and_redistributable_dlls)

- [登録 (コントロールを)](#_core_registering_controls)

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX を置き換える最新テクノロジの詳細については、「 [Activex コントロール](activex-controls.md)」を参照してください。

## <a name="ansi-or-unicode-control-versions"></a><a name="_core_ansi_or_unicode_control_versions"></a> ANSI または Unicode のコントロールバージョン

コントロールの ANSI バージョンと Unicode バージョンのどちらか、または両方を出荷するかどうかを決定する必要があります。 この決定は、ANSI および Unicode 文字セットに固有の移植性の要因に基づいています。

ANSI コントロールは、すべての Win32 オペレーティングシステム上で動作し、さまざまな Win32 オペレーティングシステムの間で最大の移植性を実現します。 Unicode コントロールは Windows NT (バージョン3.51 以降) でのみ機能しますが、Windows 95 や Windows 98 では動作しません。 移植性が重要な場合は、ANSI コントロールを出荷します。 コントロールが Windows NT 上でのみ実行される場合は、Unicode コントロールを配布できます。 また、両方の配布を選択して、ユーザーのオペレーティングシステムに最適なバージョンをアプリケーションでインストールすることもできます。

## <a name="installing-activex-controls-and-redistributable-dlls"></a><a name="_core_installing_activex_controls_and_redistributable_dlls"></a> ActiveX コントロールと再頒布可能 Dll のインストール

ActiveX コントロールによって提供されるセットアッププログラムでは、Windows ディレクトリの特別なサブディレクトリを作成し、コントロールをインストールする必要があります。ここには、OCX ファイルがあります。

> [!NOTE]
> Windows `GetWindowsDirectory` ディレクトリの名前を取得するには、セットアッププログラムで windows API を使用します。 会社または製品の名前からサブディレクトリ名を派生させることができます。

セットアッププログラムは、必要な再頒布可能 DLL ファイルを Windows システムディレクトリにインストールする必要があります。 ユーザーのコンピューターに Dll が既に存在する場合、セットアッププログラムは、インストールしているバージョンとそれらのバージョンを比較する必要があります。 ファイルのバージョン番号が既にインストールされているファイルよりも大きい場合にのみ、ファイルを再インストールします。

ActiveX コントロールは OLE コンテナーアプリケーションでのみ使用できるため、OLE Dll の完全なセットをコントロールと共に配布する必要はありません。 格納しているアプリケーション (またはオペレーティングシステム自体) に標準の OLE Dll がインストールされているとします。

## <a name="registering-controls"></a><a name="_core_registering_controls"></a> 登録 (コントロールを)

コントロールを使用する前に、Windows 登録データベースに適切なエントリを作成する必要があります。 ActiveX コントロールコンテナーの中には、ユーザーが新しいコントロールを登録するためのメニュー項目が用意されているものもありますが、この機能はすべてのコンテナーで使用できるとは限りません。 そのため、インストール時に、セットアッププログラムによってコントロールが登録されるようにすることができます。

必要に応じて、代わりにコントロールを登録するセットアッププログラムを作成できます。

Windows API を使用し `LoadLibrary` て、コントロール DLL を読み込みます。 次に、を使用して、 `GetProcAddress` "DllRegisterServer" 関数のアドレスを取得します。 最後に、関数を呼び出し `DllRegisterServer` ます。 次のコードサンプルは、 `hLib` コントロールライブラリのハンドルを格納し、 `lpDllEntryPoint` "DllRegisterServer" 関数のアドレスを格納する1つのメソッドを示しています。

[!code-cpp[NVC_MFC_AxCont#16](codesnippet/cpp/mfc-activex-controls-distributing-activex-controls_1.cpp)]

コントロールを直接登録する利点は、別のプロセスを起動して読み込む必要がないことです。つまり、REGSVR32 を使用すると、インストール時間が短縮されます。 また、登録は内部プロセスであるため、セットアッププログラムでは、外部プロセスよりもエラーや予期しない状況を処理できます。

> [!NOTE]
> セットアッププログラムで ActiveX コントロールをインストールする前に、を呼び出す必要があり `OleInitialize` ます。 セットアッププログラムが終了したら、を呼び出し `OleUnitialize` ます。 これにより、OLE システム Dll が ActiveX コントロールを登録するための適切な状態であることが保証されます。

MFCx0.DLL を登録する必要があります。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)
