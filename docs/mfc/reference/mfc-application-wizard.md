---
description: '詳細情報: MFC アプリケーションウィザード'
title: MFC アプリケーション ウィザード
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.overview
helpviewer_keywords:
- MFC Application Wizard
- executable files, creating
ms.assetid: 227ac090-921d-4b2f-be0a-66a5f4cab0d4
ms.openlocfilehash: 645f0e1ed3f1f35c109d524a8c63fa36231bc61a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219214"
---
# <a name="mfc-application-wizard"></a>MFC アプリケーション ウィザード

MFC アプリケーション ウィザードでは、コンパイル時に Windows 実行可能アプリケーション (.exe) の基本機能が実装されるアプリケーションが生成されます。 MFC の初期アプリケーションには、C++ ソース (.cpp) ファイル、リソース (.rc) ファイル、ヘッダー (.h) ファイル、およびプロジェクト (.vcxproj) ファイルが含まれます。 これらの初期ファイルで生成されるコードは、MFC に基づいています。

> [!NOTE]
> 選択したオプションに応じて、ウィザードがこの他のファイルをプロジェクトに作成します。 たとえば、[[高度な機能](../../mfc/reference/advanced-features-mfc-application-wizard.md)] ページで [**状況依存のヘルプ**] を選択すると、ウィザードによって、プロジェクトのヘルプファイルをコンパイルするために必要なファイルが作成されます。 ウィザードによって作成されるファイルの詳細については、「 [Visual Studio C++ プロジェクト用に作成されたファイルの種類](../../build/reference/file-types-created-for-visual-cpp-projects.md)」を参照し、プロジェクトの Readme.txt ファイルを参照してください。

## <a name="overview"></a>概要

ウィザードのこのページでは、作成する MFC アプリケーションの現在のアプリケーション設定が示されます。 既定では、このウィザードでは、次のようなウィザード プロジェクトが作成されます。

- [[アプリケーションの種類] (MFC アプリケーションウィザード)](../../mfc/reference/application-type-mfc-application-wizard.md)

  - タブ付きのマルチ ドキュメント インターフェイス (MDI: Multiple Document Interface) をサポートするプロジェクト。 詳細については、「 [SDI と MDI](../../mfc/sdi-and-mdi.md)」を参照してください。

  - このプロジェクトでは、 [ドキュメント/ビューアーキテクチャ](../../mfc/document-view-architecture.md)を使用します。

  - Unicode ライブラリを使用するプロジェクト

  - Visual Studio のプロジェクト形式を使用して作成された、表示形式の切り替えができるプロジェクト

  - 共有 DLL 内の MFC を使用するプロジェクト 詳細については、「 [Visual Studio での C/c + + dll の作成](../../build/dlls-in-visual-cpp.md)」を参照してください。

- [[複合ドキュメントサポート] (MFC アプリケーションウィザード)](../../mfc/reference/compound-document-support-mfc-application-wizard.md)

  - 複合ドキュメントをサポートするプロジェクト

- [[ドキュメントテンプレート文字列] (MFC アプリケーションウィザード)](../../mfc/reference/document-template-strings-mfc-application-wizard.md)

  - 既定のドキュメント テンプレート文字列としてプロジェクト名を使用するプロジェクト

- [[データベースサポート] (MFC アプリケーションウィザード)](../../mfc/reference/database-support-mfc-application-wizard.md)

  - データベースをサポートするプロジェクト

- [[ユーザーインターフェイスの機能] (MFC アプリケーションウィザード)](../../mfc/reference/user-interface-features-mfc-application-wizard.md)

  - このプロジェクトには、システムメニュー、ステータスバー、最大化および最小化ボックス、 **About** ボックス、標準のメニューバーとドッキングツールバー、子フレームなどの標準の Windows ユーザーインターフェイス機能が実装されています。

- [[高度な機能] (MFC アプリケーションウィザード)](../../mfc/reference/advanced-features-mfc-application-wizard.md)

  - 印刷と印刷プレビューをサポートするプロジェクト

  - ActiveX コントロールをサポートするプロジェクト 詳細については、「 [ActiveX コントロールを作成するための一連の操作](../../mfc/sequence-of-operations-for-creating-activex-controls.md)」を参照してください。

  - このプロジェクトでは、 [オートメーション](../../mfc/automation.md)、 [MAPI](../../mfc/mapi-support-in-mfc.md)、 [Windows ソケット](../../mfc/windows-sockets-in-mfc.md)、または Active Accessibility はサポートされていません。

  - このプロジェクトでは、 **エクスプローラー** のドッキングウィンドウ、 **出力** ドッキングペイン、および **プロパティ** のドッキングペインがサポートされています。

- [[生成されたクラス] (MFC アプリケーションウィザード)](../../mfc/reference/generated-classes-mfc-application-wizard.md)

  - プロジェクトのビュークラスは、 [CView クラス](../../mfc/reference/cview-class.md)から派生します。

  - プロジェクトのアプリケーションクラスは、 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)から派生します。

  - プロジェクトのドキュメントクラスは、 [CDocument クラス](../../mfc/reference/cdocument-class.md)から派生します。

  - プロジェクトのメインフレームクラスは、 [CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)から派生します。

  - プロジェクトの子フレームクラスは、 [CMDIChildWndEx クラス](../../mfc/reference/cmdichildwndex-class.md)から派生します。

これらの既定の設定を変更するには、ウィザードの左の列で該当するタブ タイトルをクリックし、表示されるページで必要な変更を行います。

MFC アプリケーションプロジェクトを作成した後、Visual C++ [コードウィザード](../../ide/adding-functionality-with-code-wizards-cpp.md)を使用して、プロジェクトにオブジェクトまたはコントロールを追加できます。

## <a name="see-also"></a>関連項目

[MFC アプリケーションの作成](../../mfc/reference/creating-an-mfc-application.md)<br/>
[MFC デスクトップアプリケーション](../../mfc/mfc-desktop-applications.md)<br/>
[クラスを使用して Windows 用のアプリケーションを作成する](../../mfc/using-the-classes-to-write-applications-for-windows.md)
