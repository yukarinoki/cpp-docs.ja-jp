---
title: InitInstance メンバー関数
ms.date: 11/04/2016
f1_keywords:
- InitInstance
helpviewer_keywords:
- InitInstance method [MFC]
- applications [MFC], initializing
- MFC, initializing
- initializing MFC applications
ms.assetid: 4ef09267-ff7f-4c39-91a0-57454a264f83
ms.openlocfilehash: 0a458f19f956bb1092cc76acd587bc467f25325e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625580"
---
# <a name="initinstance-member-function"></a>InitInstance メンバー関数

Windows オペレーティングシステムでは、同じアプリケーションの複数のコピー ("インスタンス") を実行できます。 `WinMain`アプリケーションの新しいインスタンスが開始されるたびに、 [InitInstance](reference/cwinapp-class.md#initinstance)を呼び出します。

`InitInstance`MFC アプリケーションウィザードによって作成される標準の実装では、次のタスクを実行します。

- 中心的なアクションとして、はドキュメント、ビュー、フレームウィンドウを作成するドキュメントテンプレートを作成します。 このプロセスの詳細については、[ドキュメントテンプレートの作成](document-template-creation.md)に関する記事をご覧ください。

- .Ini ファイルまたは Windows レジストリから、最近使用したファイルの名前を含む標準ファイルオプションを読み込みます。

- 1つ以上のドキュメントテンプレートを登録します。

- MDI アプリケーションの場合は、メインフレームウィンドウを作成します。

- コマンドラインで指定されたドキュメントを開くか、新しい空のドキュメントを開くために、コマンドラインを処理します。

独自の初期化コードを追加したり、ウィザードによって作成されたコードを変更したりできます。

> [!NOTE]
> MFC アプリケーションは、シングルスレッド アパートメント (STA) として初期化する必要があります。 オーバーライドで[CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex)を呼び出した場合は `InitInstance` 、COINIT_MULTITHREADED ではなく COINIT_APARTMENTTHREADED を指定します。

## <a name="see-also"></a>関連項目

[CWinApp: アプリケーション クラス](cwinapp-the-application-class.md)
