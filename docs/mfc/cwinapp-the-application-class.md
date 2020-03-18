---
title: 'CWinApp : アプリケーション クラス'
ms.date: 11/04/2016
helpviewer_keywords:
- application class [MFC]
- CWinApp class [MFC], CWinThread
- MFC, WinMain and
- CWinApp class [MFC], multithreading
- CWinThread class [MFC], and CWinApp
- InitApplication method [MFC]
- WinMain method [MFC]
- WinMain method [MFC], in MFC
- CWinApp class [MFC], WinMain
ms.assetid: 935822bb-d463-481b-a5f6-9719d68ed1d5
ms.openlocfilehash: 8518e21a9fa6bcf5ac640cff25b17c5028046b06
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447026"
---
# <a name="cwinapp-the-application-class"></a>CWinApp : アプリケーション クラス

MFC のメインアプリケーションクラスは、Windows オペレーティングシステム用のアプリケーションの初期化、実行、および終了をカプセル化します。 フレームワーク上に構築されたアプリケーションには、 [CWinApp](../mfc/reference/cwinapp-class.md)から派生したクラスのオブジェクトが1つだけ必要です。 このオブジェクトは、windows が作成される前に構築されます。

`CWinApp` は、アプリケーションの実行のメインスレッドを表す `CWinThread`から派生します。これは、1つまたは複数のスレッドを持つ可能性があります。 MFC の最近のバージョンでは、`InitInstance`、 **Run**、`ExitInstance`、および `OnIdle` の各メンバー関数は実際にはクラス `CWinThread`にあります。 この説明では、オブジェクトのロールがプライマリスレッドとしてではなくアプリケーションオブジェクトとして扱われるため、これらの関数については、ここでは代わりにメンバーを `CWinApp` しているかのように説明します。

> [!NOTE]
>  アプリケーションクラスは、アプリケーションの主要な実行スレッドを構成します。 Win32 API 関数を使用すると、実行のセカンダリスレッドを作成することもできます。 これらのスレッドは、MFC ライブラリを使用できます。 詳細については、「[マルチスレッド](../parallel/multithreading-support-for-older-code-visual-cpp.md)」を参照してください。

Windows オペレーティングシステムの任意のプログラムと同様に、フレームワークアプリケーションには `WinMain` 機能があります。 ただし、フレームワークアプリケーションでは、`WinMain`は記述しません。 これはクラスライブラリによって提供され、アプリケーションの起動時に呼び出されます。 `WinMain` は、ウィンドウクラスの登録などの標準的なサービスを実行します。 次に、アプリケーションオブジェクトのメンバー関数を呼び出して、アプリケーションを初期化して実行します。 (`WinMain` をカスタマイズするには、を呼び出し `WinMain` `CWinApp` メンバー関数をオーバーライドします)。

アプリケーションを初期化するために、`WinMain` はアプリケーションオブジェクトの `InitApplication` と `InitInstance` メンバー関数を呼び出します。 アプリケーションのメッセージループを実行するために、`WinMain` は**実行**メンバー関数を呼び出します。 終了時に、`WinMain` はアプリケーションオブジェクトの `ExitInstance` メンバー関数を呼び出します。

> [!NOTE]
>  このドキュメントで**太字**で示されている名前は、Microsoft Foundation Class ライブラリとビジュアルC++によって提供される要素を示しています。 `monospaced` 型に表示される名前は、作成またはオーバーライドする要素を示します。

## <a name="see-also"></a>参照

[MFC の一般的なトピック](../mfc/general-mfc-topics.md)<br/>
[CWinApp および MFC アプリケーション ウィザード](../mfc/cwinapp-and-the-mfc-application-wizard.md)<br/>
[オーバーライド可能な CWinApp のメンバー関数](../mfc/overridable-cwinapp-member-functions.md)<br/>
[CWinApp のその他のサービス](../mfc/special-cwinapp-services.md)
