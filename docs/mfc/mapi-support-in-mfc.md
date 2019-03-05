---
title: MFC での MAPI サポート
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, MAPI support
- MAPI support in MFC
- CDocument class [MFC], and MAPI
- OnUpdateFileSendMail method [MFC]
- MAPI, MFC
- OnFileSendMail method [MFC]
ms.assetid: cafbecb1-0427-4077-b4b8-159bae5b49b8
ms.openlocfilehash: 9b873ca1b3384adab6487fb3af9dc1401aaad12c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281643"
---
# <a name="mapi-support-in-mfc"></a>MFC での MAPI サポート

MFC の Microsoft メッセージング アプリケーション プログラム インターフェイス (MAPI) クラスでのサブセットのサポートを提供する`CDocument`します。 具体的には、`CDocument`メール サポートがエンドユーザーのコンピューター上に存在するかどうかを決定するメンバー関数があり、そうである場合は、標準コマンド ID が判定メール送信コマンドを有効にします。 このコマンドの MFC のハンドラー関数は、電子メールでドキュメントを送信できます。

> [!TIP]
>  MFC は、全体の MAPI 関数のセットをカプセル化しない、まだ関数を呼び出すできます MAPI 同様、直接、MFC プログラムから直接、Win32 API 関数を呼び出すことができます。

コマンドは、アプリケーションではメールの送信を提供することは非常に簡単です。 MFC はドキュメントをパッケージ化する実装を提供します (つまり、 `CDocument`-派生オブジェクト) 添付ファイルとしてメールとして送信するとします。 この添付ファイルは保存するファイルの保存のコマンドと同じです (シリアル化) メール メッセージに、ドキュメントの内容。 メールの宛先と件名とメッセージのテキスト メッセージを追加する機会を付与するためにユーザーのコンピューター上のメール クライアントと、この実装を呼び出します。 ユーザーは、その一般的なメール アプリケーションのユーザー インターフェイスを参照してください。 この機能は、2 つのによって提供される`CDocument`メンバー関数:`OnFileSendMail`と`OnUpdateFileSendMail`します。

MAPI の添付ファイルを送信するファイルを読み取る必要があります。 アプリケーションは保持、データ ファイルの中に開いている場合、`OnFileSendMail`関数の呼び出し、ファイルを複数のプロセス、ファイルへのアクセスを許可する共有モードで開く必要があります。

> [!NOTE]
>  オーバーライド元のバージョンの`OnFileSendMail`クラスの`COleDocument`正しくハンドル複合ドキュメント。

#### <a name="to-implement-a-send-mail-command-with-mfc"></a>MFC での送信 コマンドを実装するには

1. コマンド ID が判定するメニュー項目を追加するのにには、Visual C のメニュー エディターを使用します。

   このコマンド ID は、コマによって提供されます。H. 任意のメニューにコマンドを追加できますが、通常に追加されて、**ファイル**メニュー。

1. ドキュメントのメッセージ マップに、次を手動で追加するには。

   [!code-cpp[NVC_MFCDocView#9](../mfc/codesnippet/cpp/mapi-support-in-mfc_1.cpp)]

    > [!NOTE]
    >  このメッセージ マップのいずれかから派生したドキュメントが適して`CDocument`または`COleDocument`-場合でも、メッセージ マップは、ドキュメントの派生クラスで、いずれの場合も、適切な基本クラスを選択します。

1. アプリケーションをビルドします。

MFC が使用してメニュー項目でメール サポートを使用できる場合`OnUpdateFileSendMail`後にコマンドを処理および`OnFileSendMail`します。 メールのサポートが利用できない場合は、MFC で、ユーザーに表示しないように、メニュー項目が自動的に削除されます。

> [!TIP]
>  前述したように、メッセージ マップ エントリを手動で追加することがなく、メッセージを関数にマップするのにクラスのプロパティ ウィンドウを使用できます。 詳細については、次を参照してください。[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md)します。

関連情報については、次を参照してください。、 [MAPI](../mfc/mapi.md)の概要。

詳細については、 `CDocument` MAPI を有効にするメンバー関数を参照してください。

- [CDocument::OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)

- [CDocument::OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)

- [COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)

## <a name="see-also"></a>関連項目

[MAPI](../mfc/mapi.md)
