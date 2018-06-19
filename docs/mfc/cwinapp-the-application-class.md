---
title: 'CWinApp: アプリケーション クラス |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CWinApp
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0c3641441554d73e0c7657dd220be86f0c0cab0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343006"
---
# <a name="cwinapp-the-application-class"></a>CWinApp : アプリケーション クラス
MFC では、アプリケーションのメイン クラスには、初期化、実行、および Windows オペレーティング システム用のアプリケーションの終了がカプセル化します。 フレームワーク上に構築されたアプリケーションには、いずれかが必要し、から派生したクラスのオブジェクトを 1 つだけ[CWinApp](../mfc/reference/cwinapp-class.md)です。 Windows が作成される前に、このオブジェクトが構築されます。  
  
 `CWinApp` 派生した`CWinThread`、1 つまたは複数のスレッドがありますアプリケーションの実行のメイン スレッドを表します。 MFC では、最近のバージョンで、 `InitInstance`、**実行**、 `ExitInstance`、および`OnIdle`クラス メンバー関数が実際に`CWinThread`です。 場合と同様、これらの関数はここで説明`CWinApp`メンバー代わりに、説明は、プライマリ スレッドではなくアプリケーション オブジェクトとして、オブジェクトの役割に関係しているためです。  
  
> [!NOTE]
>  アプリケーション クラスは、アプリケーションのプライマリ スレッドの実行を構成します。 Win32 API 関数を使用して、セカンダリ スレッドを作成することもできます。 これらのスレッドには、MFC ライブラリを使用できます。 詳細については、次を参照してください。[マルチ スレッド](../parallel/multithreading-support-for-older-code-visual-cpp.md)です。  
  
 Windows オペレーティング システムの任意のプログラムと同様に、フレームワーク アプリケーションがあります、`WinMain`関数。 Framework アプリケーションでただし、作成しません`WinMain`です。 クラス ライブラリによって提供され、アプリケーションが起動するときに呼び出されます。 `WinMain` ウィンドウ クラスの登録などの標準的なサービスを実行します。 呼び出してメンバーを初期化し、アプリケーションを実行するアプリケーション オブジェクトの機能です。 (をカスタマイズできます`WinMain`オーバーライドすることで、`CWinApp`メンバー関数を`WinMain`呼び出し)。  
  
 アプリケーションを初期化するために`WinMain`アプリケーション オブジェクトの`InitApplication`と`InitInstance`メンバー関数。 アプリケーションのメッセージ ループを実行する`WinMain`呼び出し、**実行**メンバー関数。 、終了時に`WinMain`アプリケーション オブジェクトを呼び出して、`ExitInstance`メンバー関数。  
  
> [!NOTE]
>  表示される名前**太字**このドキュメントでは、Microsoft Foundation Class ライブラリと Visual C によって指定された要素を指定します。 表示される名前`monospaced`型が作成または上書きする要素を示しています。  
  
## <a name="see-also"></a>関連項目  
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)   
 [CWinApp および MFC アプリケーション ウィザード](../mfc/cwinapp-and-the-mfc-application-wizard.md)   
 [オーバーライド可能な CWinApp のメンバー関数します。](../mfc/overridable-cwinapp-member-functions.md)   
 [CWinApp のその他のサービス](../mfc/special-cwinapp-services.md)

