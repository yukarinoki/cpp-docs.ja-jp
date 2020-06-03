---
title: MFC アプリケーション ウィザード
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.overview
helpviewer_keywords:
- MFC Application Wizard
- executable files, creating
ms.assetid: 227ac090-921d-4b2f-be0a-66a5f4cab0d4
ms.openlocfilehash: 6949f136890e8274f225a49496b2eb1b8f78b6fc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351834"
---
# <a name="mfc-application-wizard"></a>MFC アプリケーション ウィザード

MFC アプリケーション ウィザードでは、コンパイル時に Windows 実行可能アプリケーション (.exe) の基本機能が実装されるアプリケーションが生成されます。 MFC の初期アプリケーションには、C++ ソース (.cpp) ファイル、リソース (.rc) ファイル、ヘッダー (.h) ファイル、およびプロジェクト (.vcxproj) ファイルが含まれます。 これらの初期ファイルで生成されるコードは、MFC に基づいています。

> [!NOTE]
> 選択したオプションに応じて、ウィザードがこの他のファイルをプロジェクトに作成します。 たとえば、[[高度な機能]](../../mfc/reference/advanced-features-mfc-application-wizard.md)ページで [**状況依存のヘルプ**] を選択した場合、ウィザードはプロジェクトのヘルプ ファイルをコンパイルするために必要なファイルを作成します。 ウィザードによって作成されるファイルの詳細については[、「Visual Studio C++ プロジェクト用に作成されたファイルの種類](../../build/reference/file-types-created-for-visual-cpp-projects.md)」および「プロジェクトの Readme.txt ファイル」を参照してください。

## <a name="overview"></a>概要

ウィザードのこのページでは、作成する MFC アプリケーションの現在のアプリケーション設定が示されます。 既定では、このウィザードでは、次のようなウィザード プロジェクトが作成されます。

- [アプリケーションの種類、MFC アプリケーション ウィザード](../../mfc/reference/application-type-mfc-application-wizard.md)

  - タブ付きのマルチ ドキュメント インターフェイス (MDI: Multiple Document Interface) をサポートするプロジェクト。 詳細については、「 [SDI および MDI](../../mfc/sdi-and-mdi.md)」を参照してください。

  - プロジェクトでは[、ドキュメント/ビュー アーキテクチャ](../../mfc/document-view-architecture.md)を使用します。

  - Unicode ライブラリを使用するプロジェクト

  - Visual Studio のプロジェクト形式を使用して作成された、表示形式の切り替えができるプロジェクト

  - 共有 DLL 内の MFC を使用するプロジェクト 詳細については、「 [Visual Studio で C/C++ DLL を作成する](../../build/dlls-in-visual-cpp.md)」を参照してください。

- [複合ドキュメントのサポート、MFC アプリケーション ウィザード](../../mfc/reference/compound-document-support-mfc-application-wizard.md)

  - 複合ドキュメントをサポートするプロジェクト

- [ドキュメント テンプレート文字列、MFC アプリケーション ウィザード](../../mfc/reference/document-template-strings-mfc-application-wizard.md)

  - 既定のドキュメント テンプレート文字列としてプロジェクト名を使用するプロジェクト

- [データベース サポート、MFC アプリケーション ウィザード](../../mfc/reference/database-support-mfc-application-wizard.md)

  - データベースをサポートするプロジェクト

- [ユーザー インターフェイス機能、MFC アプリケーション ウィザード](../../mfc/reference/user-interface-features-mfc-application-wizard.md)

  - このプロジェクトでは、システム メニュー、ステータス バー、最大化と最小化ボックス、**情報**ボックス、標準メニュー バーとドッキング ツールバー、子フレームなどの Windows 標準ユーザー インターフェイス機能が実装されています。

- [高度な機能、MFC アプリケーション ウィザード](../../mfc/reference/advanced-features-mfc-application-wizard.md)

  - 印刷と印刷プレビューをサポートするプロジェクト

  - ActiveX コントロールをサポートするプロジェクト 詳細については、「 [ActiveX コントロールを作成するための操作のシーケンス](../../mfc/sequence-of-operations-for-creating-activex-controls.md)」を参照してください。

  - このプロジェクトでは、[オートメーション](../../mfc/automation.md) [、MAPI、Windows](../../mfc/mapi-support-in-mfc.md)[ソケット](../../mfc/windows-sockets-in-mfc.md)、またはアクティブなアクセシビリティのサポートは提供されません。

  - プロジェクトは **、エクスプローラー**ドッキング ペイン、**出力**ドッキング ペイン、および**プロパティ**ドッキング ペインをサポートします。

- [生成されたクラス、MFC アプリケーション ウィザード](../../mfc/reference/generated-classes-mfc-application-wizard.md)

  - プロジェクトのビュー クラスは[CView クラス](../../mfc/reference/cview-class.md)から派生します。

  - プロジェクトのアプリケーション クラスは[、CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)から派生します。

  - プロジェクトのドキュメント クラスは、 [CDocument クラス](../../mfc/reference/cdocument-class.md)から派生します。

  - プロジェクトのメイン フレーム クラスは[、CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)から派生します。

  - プロジェクトの子フレーム クラスは[、CMDIChildWndEx クラス](../../mfc/reference/cmdichildwndex-class.md)から派生します。

これらの既定の設定を変更するには、ウィザードの左の列で該当するタブ タイトルをクリックし、表示されるページで必要な変更を行います。

MFC アプリケーション プロジェクトを作成した後、Visual C++[コード ウィザード](../../ide/adding-functionality-with-code-wizards-cpp.md)を使用して、プロジェクトにオブジェクトまたはコントロールを追加できます。

## <a name="see-also"></a>関連項目

[MFC アプリケーションの作成](../../mfc/reference/creating-an-mfc-application.md)<br/>
[MFC デスクトップ アプリケーション](../../mfc/mfc-desktop-applications.md)<br/>
[クラスを使用した Windows アプリケーションの作成](../../mfc/using-the-classes-to-write-applications-for-windows.md)
