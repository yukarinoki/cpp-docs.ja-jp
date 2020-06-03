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
ms.openlocfilehash: 3024f744407cf33c8dfad8a6f7af736e0f8061ef
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81357002"
---
# <a name="mapi-support-in-mfc"></a>MFC での MAPI サポート

MFC では、クラス`CDocument`の Microsoft メッセージング アプリケーション プログラム インターフェイス (MAPI) のサブセットをサポートしています。 具体的には`CDocument`、エンド ユーザーのマシンにメール サポートがあるかどうかを決定するメンバー関数があり、存在する場合は、標準のコマンド ID がID_FILE_SEND_MAILのメール送信コマンドを有効にします。 このコマンドの MFC ハンドラー関数を使用すると、ユーザーは電子メールでドキュメントを送信できます。

> [!TIP]
> MFC では、MAPI 関数セット全体をカプセル化するわけではありませんが、MFC プログラムから直接 Win32 API 関数を呼び出すことができるのと同様に、MAPI 関数を直接呼び出すことができます。

アプリケーションでメール送信コマンドを指定するのは非常に簡単です。 MFC では、ドキュメント (`CDocument`つまり、派生オブジェクト) を添付ファイルとしてパッケージ化し、メールとして送信する実装が提供されます。 この添付ファイルは、ドキュメントの内容をメール メッセージに保存 (シリアル化) する [ファイルの保存] コマンドと同じです。 この実装では、ユーザーのコンピュータ上のメール クライアントに対して、メールのアドレス指定やメール メッセージへの件名とメッセージ テキストの追加を行う機会をユーザーに提供します。 ユーザーには、使い慣れたメール アプリケーションのユーザー インターフェイスが表示されます。 この機能は、`CDocument``OnFileSendMail`と`OnUpdateFileSendMail`の 2 つのメンバー関数によって提供されます。

MAPI は、添付ファイルを送信するファイルを読み取る必要があります。 アプリケーションが関数呼び出し中にデータ`OnFileSendMail`・ファイルをオープンしたままにする場合、複数のプロセスがファイルにアクセスできるようにする共有モードでファイルを開く必要があります。

> [!NOTE]
> クラス`OnFileSendMail``COleDocument`のオーバーライド バージョンは、複合ドキュメントを正しく処理します。

#### <a name="to-implement-a-send-mail-command-with-mfc"></a>MFC を使用してメール送信コマンドを実装するには

1. Visual C++ メニュー エディターを使用して、コマンド ID がID_FILE_SEND_MAILのメニュー項目を追加します。

   このコマンド ID は、AFXRES のフレームワークによって提供されます。H。 コマンドは任意のメニューに追加できますが、通常は **[ファイル]** メニューに追加されます。

1. ドキュメントのメッセージ マップに次の項目を手動で追加します。

   [!code-cpp[NVC_MFCDocView#9](../mfc/codesnippet/cpp/mapi-support-in-mfc_1.cpp)]

    > [!NOTE]
    >  このメッセージ マップは、派生ドキュメント クラス`CDocument`に`COleDocument`メッセージ マップがある場合でも、どちらの場合も正しい基本クラスを取得するか、またはから派生したドキュメントに対して機能します。

1. アプリケーションをビルドします。

メールサポートが利用可能な場合、MFC はメニュー項目`OnUpdateFileSendMail`を を 有効にし`OnFileSendMail`、その後で コマンドを 処理します。 メールサポートが利用できない場合、MFC は自動的にメニュー項目を削除するので、ユーザーには表示されません。

> [!TIP]
> 前述のようにメッセージ マップ エントリを手動で追加する代わりに、[クラス クラス ウィザード](reference/mfc-class-wizard.md)を使用してメッセージを関数にマップできます。 詳細については、「[関数へのメッセージのマッピング](../mfc/reference/mapping-messages-to-functions.md)」を参照してください。

関連情報については[、MAPI](../mfc/mapi.md)の概要を参照してください。

MAPI を有効に`CDocument`するメンバー関数の詳細については、次を参照してください。

- [Cドキュメント::オンファイル送信メール](../mfc/reference/cdocument-class.md#onfilesendmail)

- [Cドキュメント::オンアップデートファイル送信メール](../mfc/reference/cdocument-class.md#onupdatefilesendmail)

- [ファイル送信メール](../mfc/reference/coledocument-class.md#onfilesendmail)

## <a name="see-also"></a>関連項目

[MAPI](../mfc/mapi.md)
