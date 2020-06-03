---
title: '方法: 再起動マネージャーのサポートを追加する'
ms.date: 11/04/2016
helpviewer_keywords:
- Restart manager [MFC]
- C++, application crash support
ms.assetid: 7f3f5867-d4bc-4ba8-b3c9-dc1e7be93642
ms.openlocfilehash: 7cf3fede663a7c4bc85573e17dd9c2f8bf3622b4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373313"
---
# <a name="how-to-add-restart-manager-support"></a>方法: 再起動マネージャーのサポートを追加する

再起動マネージャーは、Windows Vista 以降のオペレーティング システム用の Visual Studio に追加された機能です。 再起動マネージャーにより、アプリケーションが予期せずに終了または再起動した場合のアプリケーションのサポートが強化されます。 再起動マネージャーの動作は、アプリケーションの種類によって異なります。 アプリケーションがドキュメント エディターの場合、再起動マネージャーは、アプリケーションが予期せずに終了したら、開いているドキュメントの状態と内容をアプリケーションが自動的に保存できるようにし、アプリケーションを再起動します。 アプリケーションがドキュメント エディターではない場合、再起動マネージャーは、アプリケーションを再起動しますが、既定ではアプリケーションの状態を保存できません。

Unicode アプリケーションは、再起動後、タスク ダイアログ ボックスを表示します。 ANSI アプリケーションは、Windows メッセージ ボックスを表示します。 この時点で、ユーザーは自動的に保存されたドキュメントを復元するかどうかを選択します。 自動的に保存されたドキュメントをユーザーが復元しない場合は、再起動マネージャーによって一時ファイルが破棄されます。

> [!NOTE]
> データの保存とアプリケーションの再起動を行う再起動マネージャーの既定の動作はオーバーライドできます。

既定では、Visual Studio のプロジェクト ウィザードを使用して作成された MFC アプリケーションは、Windows Vista 以降のオペレーティング システムを持つコンピューターでアプリケーションを実行する場合に、再起動マネージャーをサポートします。 アプリケーションが再起動マネージャーをサポートしないようにする場合は、新しいプロジェクト ウィザードで再起動マネージャーを無効にすることができます。

### <a name="to-add-support-for-the-restart-manager-to-an-existing-application"></a>既存のアプリケーションが再起動マネージャーをサポートするように設定するには

1. 既存の MFC アプリケーションを Visual Studio で開きます。

1. メイン アプリケーションのソース ファイルを開きます。 既定では、これはアプリケーションと同じ名前の .cpp ファイルです。 たとえば、MyProject のメイン アプリケーションのソース ファイルは、MyProject.cpp です。

1. メイン アプリケーションのコンストラクターを探します。 たとえば、プロジェクトが MyProject である場合、コンストラクターは `CMyProjectApp::CMyProjectApp()`です。

1. 次のコード行をコンストラクターに追加します。

```
    m_dwRestartManagerSupportFlags = AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS;
```

1. アプリケーションの `InitInstance` メソッドが、その親の `InitInstance` メソッド ( [CWinApp::InitInstance](../mfc/reference/cwinapp-class.md#initinstance) または `CWinAppEx::InitInstance`に追加された機能です。 メソッド`InitInstance`は *、m_dwRestartManagerSupportFlags*パラメーターをチェックします。

1. アプリケーションをコンパイルして実行します。

## <a name="see-also"></a>関連項目

[クラス](../mfc/reference/cdatarecoveryhandler-class.md)<br/>
[CWinApp::m_dwRestartManagerSupportFlags](../mfc/reference/cwinapp-class.md#m_dwrestartmanagersupportflags)<br/>
[CWinApp クラス](../mfc/reference/cwinapp-class.md)<br/>
[CWinApp::m_nAutosaveInterval](../mfc/reference/cwinapp-class.md#m_nautosaveinterval)<br/>
[Cドキュメント::オンドキュメントイベント](../mfc/reference/cdocument-class.md#ondocumentevent)
