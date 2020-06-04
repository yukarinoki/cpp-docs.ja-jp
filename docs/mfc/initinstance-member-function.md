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
ms.openlocfilehash: 2cf5b266348e299fe761ba40bd2cfb849f02b9ab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377193"
---
# <a name="initinstance-member-function"></a>InitInstance メンバー関数

Windows オペレーティング システムでは、同じアプリケーションの複数のコピー ("インスタンス") を実行できます。 `WinMain`アプリケーションの新しいインスタンスが起動するたびに[InitInstance](../mfc/reference/cwinapp-class.md#initinstance)を呼び出します。

MFC`InitInstance`アプリケーション ウィザードによって作成される標準の実装では、次のタスクが実行されます。

- その中心的なアクションとして、ドキュメント、ビュー、およびフレーム ウィンドウを作成するドキュメント テンプレートを作成します。 このプロセスの詳細については、「[ドキュメント テンプレートの作成](../mfc/document-template-creation.md)」を参照してください。

- .ini ファイルまたは Windows レジストリから、最近使用したファイルの名前を含む標準ファイル オプションを読み込みます。

- 1 つ以上のドキュメント テンプレートを登録します。

- MDI アプリケーションの場合、メイン フレーム ウィンドウを作成します。

- コマンド ラインで指定されたドキュメントを開くか、新しい空のドキュメントを開くために、コマンド ラインを処理します。

独自の初期化コードを追加したり、ウィザードによって作成されたコードを変更したりできます。

> [!NOTE]
> MFC アプリケーションは、シングルスレッド アパートメント (STA) として初期化する必要があります。 オーバーライドで[CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex)を`InitInstance`呼び出す場合は、COINIT_MULTITHREADEDではなくCOINIT_APARTMENTTHREADEDを指定します。

## <a name="see-also"></a>関連項目

[CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)
