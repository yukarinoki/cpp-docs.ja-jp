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
ms.openlocfilehash: 007a4e53fd9b3eae612947cd76ee352776572d4f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373522"
---
# <a name="cwinapp-the-application-class"></a>CWinApp : アプリケーション クラス

MFC のメイン アプリケーション クラスは、Windows オペレーティング システムのアプリケーションの初期化、実行、および終了をカプセル化します。 フレームワーク上に構築されたアプリケーションは[、CWinApp](../mfc/reference/cwinapp-class.md)から派生したクラスのオブジェクトを 1 つだけ持つ必要があります。 このオブジェクトは、ウィンドウが作成される前に構築されます。

`CWinApp`は`CWinThread`、アプリケーションのメインスレッドを表す から派生します。 MFC の最近のバージョンでは`InitInstance`、 、 `ExitInstance`**実行**、および`OnIdle`メンバー関数は`CWinThread`実際にはクラスに含まれています。 これらの関数は、オブジェクトのプライマリ スレッドではなく`CWinApp`アプリケーション オブジェクトとしての役割に関する議論が関係するため、ここでは、メンバーであるかのように説明されています。

> [!NOTE]
> アプリケーション クラスは、アプリケーションのプライマリスレッドの実行を構成します。 Win32 API 関数を使用すると、実行のセカンダリ スレッドを作成することもできます。 これらのスレッドは、MFC ライブラリを使用できます。 詳細については、「[マルチスレッド」を](../parallel/multithreading-support-for-older-code-visual-cpp.md)参照してください。

Windows オペレーティング システムのプログラムと同様に、フレームワーク アプリケーション`WinMain`にも機能があります。 ただし、フレームワーク アプリケーションでは、 を記述`WinMain`しません。 これはクラス ライブラリによって提供され、アプリケーションの起動時に呼び出されます。 `WinMain`は、ウィンドウ クラスの登録などの標準サービスを実行します。 次に、アプリケーション オブジェクトのメンバー関数を呼び出して、アプリケーションを初期化して実行します。 (呼`WinMain`び出`WinMain`すメンバー関数を`CWinApp`オーバーライドしてカスタマイズできます)。

アプリケーションを初期化するには、`WinMain`アプリケーション オブジェクト`InitApplication`と`InitInstance`メンバー関数を呼び出します。 アプリケーションのメッセージ ループを実行するには`WinMain`**、Run**メンバー関数を呼び出します。 終了時に、`WinMain`アプリケーション オブジェクトのメンバー関数`ExitInstance`を呼び出します。

> [!NOTE]
> このドキュメントで**太字**で示されている名前は、Microsoft ファウンデーション クラス ライブラリおよび Visual C++ によって提供される要素を示します。 型に表示`monospaced`される名前は、作成またはオーバーライドする要素を示します。

## <a name="see-also"></a>関連項目

[MFC の一般的なトピック](../mfc/general-mfc-topics.md)<br/>
[CWinApp および MFC アプリケーション ウィザード](../mfc/cwinapp-and-the-mfc-application-wizard.md)<br/>
[オーバーライド可能な CWinApp メンバー関数](../mfc/overridable-cwinapp-member-functions.md)<br/>
[CWinApp のその他のサービス](../mfc/special-cwinapp-services.md)
