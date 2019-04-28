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
ms.openlocfilehash: c96d009cf19981a475209233ee397af1cdcb352d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219521"
---
# <a name="initinstance-member-function"></a>InitInstance メンバー関数

Windows オペレーティング システムは、複数のコピー、または「インスタンス」の同じアプリケーションを実行することができます。 `WinMain` 呼び出し[InitInstance](../mfc/reference/cwinapp-class.md#initinstance)たびに、アプリケーションの新しいインスタンスを開始します。

標準`InitInstance`MFC アプリケーション ウィザードによって作成された実装は、次のタスクを実行します。

- 中央のアクションとしては、ドキュメント、ビュー、およびフレーム ウィンドウを作成するドキュメント テンプレートを作成します。 このプロセスの説明は、次を参照してください。[ドキュメント テンプレートの作成](../mfc/document-template-creation.md)です。

- .Ini ファイルまたは最近使用したファイルの名前を含む、Windows レジストリから標準のファイル オプションを読み込みます。

- 1 つまたは複数のドキュメント テンプレートを登録します。

- MDI アプリケーションのメイン フレーム ウィンドウを作成します。

- コマンドラインで指定されたドキュメントを開くか、新しい空の文書を開くには、コマンド ラインを処理します。

独自の初期化コードを追加したり、ウィザードによって作成されたコードを変更することができます。

> [!NOTE]
>  MFC アプリケーションは、シングルスレッド アパートメント (STA) として初期化する必要があります。 呼び出す場合[CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex)で、`InitInstance`オーバーライド、COINIT_APARTMENTTHREADED (COINIT_MULTITHREADED ではなく) を指定します。

## <a name="see-also"></a>関連項目

[CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)
