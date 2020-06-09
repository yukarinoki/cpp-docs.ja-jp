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
ms.openlocfilehash: e8327cf55606131d43201aa1f4f51526bcba147a
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617063"
---
# <a name="cwinapp-the-application-class"></a>CWinApp : アプリケーション クラス

MFC のメインアプリケーションクラスは、Windows オペレーティングシステム用のアプリケーションの初期化、実行、および終了をカプセル化します。 フレームワーク上に構築されたアプリケーションには、 [CWinApp](reference/cwinapp-class.md)から派生したクラスのオブジェクトが1つだけ必要です。 このオブジェクトは、windows が作成される前に構築されます。

`CWinApp`は `CWinThread` 、アプリケーションの実行のメインスレッドを表すから派生します。これは、1つ以上のスレッドを持つ場合があります。 MFC の最近のバージョンでは、、 `InitInstance` **Run**、 `ExitInstance` 、およびの各 `OnIdle` メンバー関数は実際にはクラスに含まれてい `CWinThread` ます。 この説明では、 `CWinApp` オブジェクトのロールがプライマリスレッドではなくアプリケーションオブジェクトとして扱われるため、ここではこれらの関数をメンバーであるかのように説明します。

> [!NOTE]
> アプリケーションクラスは、アプリケーションの主要な実行スレッドを構成します。 Win32 API 関数を使用すると、実行のセカンダリスレッドを作成することもできます。 これらのスレッドは、MFC ライブラリを使用できます。 詳細については、「[マルチスレッド](../parallel/multithreading-support-for-older-code-visual-cpp.md)」を参照してください。

Windows オペレーティングシステムの任意のプログラムと同様に、フレームワークアプリケーションには関数があり `WinMain` ます。 ただし、フレームワークアプリケーションでは、を記述しません `WinMain` 。 これはクラスライブラリによって提供され、アプリケーションの起動時に呼び出されます。 `WinMain`ウィンドウクラスの登録など、標準的なサービスを実行します。 次に、アプリケーションオブジェクトのメンバー関数を呼び出して、アプリケーションを初期化して実行します。 (を `WinMain` 呼び出すメンバー関数をオーバーライドすることにより、をカスタマイズでき `CWinApp` `WinMain` ます)。

アプリケーションを初期化するために、は `WinMain` アプリケーションオブジェクト `InitApplication` と `InitInstance` メンバー関数を呼び出します。 アプリケーションのメッセージループを実行するために、は `WinMain` **実行**メンバー関数を呼び出します。 終了時に、は `WinMain` アプリケーションオブジェクトの `ExitInstance` メンバー関数を呼び出します。

> [!NOTE]
> このドキュメントで**太字**で示されている名前は、Microsoft Foundation Class ライブラリおよび Visual C++ によって提供される要素を示しています。 型に表示さ `monospaced` れる名前は、作成またはオーバーライドする要素を示します。

## <a name="see-also"></a>関連項目

[MFC の一般的なトピック](general-mfc-topics.md)<br/>
[CWinApp および MFC アプリケーション ウィザード](cwinapp-and-the-mfc-application-wizard.md)<br/>
[オーバーライド可能な CWinApp メンバー関数](overridable-cwinapp-member-functions.md)<br/>
[CWinApp のその他のサービス](special-cwinapp-services.md)
