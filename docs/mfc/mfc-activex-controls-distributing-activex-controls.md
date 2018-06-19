---
title: 'MFC ActiveX コントロール: ActiveX コントロールの配布 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- GetWindowsDirectory
- GetSystemDirectory
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c6658c972b9d9cdeececd43a89ac424964d2289
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358808"
---
# <a name="mfc-activex-controls-distributing-activex-controls"></a>MFC ActiveX コントロール : ActiveX コントロールの配布
この記事では、ActiveX コントロールを再配布に関連するいくつかの問題について説明します。  
  
-   [ANSI または Unicode コントロールのバージョン](#_core_ansi_or_unicode_control_versions)  
  
-   [ActiveX コントロールと再頒布可能 Dll をインストールします。](#_core_installing_activex_controls_and_redistributable_dlls)  
  
-   [コントロールの登録](#_core_registering_controls)  
  
##  <a name="_core_ansi_or_unicode_control_versions"></a> ANSI または Unicode コントロールのバージョン  
 コントロール、または両方の ANSI または Unicode のバージョンに付属するかどうかを決定する必要があります。 この決定は、ANSI と Unicode の文字セットに固有の移植性の要因に基づいています。  
  
 ANSI コントロールは、すべての Win32 オペレーティング システムで動作するは、さまざまな Win32 オペレーティング システム間で最大の移植性を許可します。 Unicode のコントロールは、Windows NT (version 3.51 以降) だけではなく Windows 95 または Windows 98 に動作します。 移植性が重視される場合、ANSI コントロールである場合。 コントロールは、Windows NT でのみ実行される場合、は、Unicode コントロールを出荷することができます。 両方の出荷を用意し、アプリケーションがユーザーのオペレーティング システムに最適のバージョンをインストールする可能性がありますもできます。  
  
##  <a name="_core_installing_activex_controls_and_redistributable_dlls"></a> ActiveX コントロールと再頒布可能 Dll をインストールします。  
 ActiveX コントロールを提供するセットアップ プログラムは、特別な Windows ディレクトリのサブディレクトリを作成し、コントロールのインストールする必要があります。OCX ファイルが入っています。  
  
> [!NOTE]
>  Windows を使用して**GetWindowsDirectory**セットアップ プログラムでの API は、Windows ディレクトリの名前を取得します。 サブディレクトリ名を見て会社または製品の名前から派生することがあります。  
  
 セットアップ プログラムは、Windows システム ディレクトリに必要な再頒布可能 DLL ファイルをインストールする必要があります。 Dll のいずれかがユーザーのコンピューターに存在、する場合、セットアップ プログラム必要があります、それらのバージョンをインストールするバージョンとを比較します。 そのバージョン番号が既にインストールされているファイルよりも高い場合にのみ、ファイルを再インストールします。  
  
 ActiveX コントロールは、OLE コンテナー アプリケーションでのみ使用できる、ために、コントロールと OLE Dll の完全なセットを配布する必要はありません。 コンテナー アプリケーション (またはオペレーティング システム自体) が、標準的な OLE インストールされている Dll を想定することができます。  
  
##  <a name="_core_registering_controls"></a> コントロールの登録  
 コントロールを使用することができます、前に、Windows レジストリ データベースにその適切なエントリが作成する必要があります。 一部の ActiveX コントロール コンテナーは、新しいコントロールを登録するユーザーのメニュー項目を提供しますが、この機能は、すべてのコンテナーで使用できない可能性があります。 そのため、セットアップ プログラムがインストールされている場合に、コントロールを登録することができます。  
  
 場合は、代わりに直接コントロールを登録するセットアップ プログラムを記述することができます。  
  
 使用して、 **LoadLibrary** Windows API コントロール DLL を読み込めません。 次に、使用**GetProcAddress** "DllRegisterServer"関数のアドレスを取得します。 最後を呼び出して、`DllRegisterServer`関数。 次のコード サンプルでは 1 つの可能なメソッドを`hLib`コントロール ライブラリのハンドルを格納および`lpDllEntryPoint`"DllRegisterServer"関数のアドレスを格納します。  
  
 [!code-cpp[NVC_MFC_AxCont#16](../mfc/codesnippet/cpp/mfc-activex-controls-distributing-activex-controls_1.cpp)]  
  
 コントロールの直接登録の利点は、する必要はありませんを起動し、別のプロセス (つまり、REGSVR32) を読み込むインストール時間を短縮です。 さらに、登録は、内部プロセスであるため、セットアップ プログラムはエラーを処理できるし、予期しない状況は外部プロセスをよりことができます。  
  
> [!NOTE]
>  呼び出す必要がありますが、セットアップ プログラムは、ActiveX コントロールをインストールする前に**OleInitialize**です。 セットアップ プログラムが完了したら、呼び出す**OleUnitialize**です。 これにより、OLE システム Dll が ActiveX コントロールを登録するための適切な状態であります。  
  
 MFCx0.DLL を登録する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

