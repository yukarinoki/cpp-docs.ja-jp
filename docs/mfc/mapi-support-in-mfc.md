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
ms.openlocfilehash: 7eff22b2a7b4c838f2967fb5217b9dec96903d0e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625568"
---
# <a name="mapi-support-in-mfc"></a>MFC での MAPI サポート

MFC では、クラスの Microsoft メッセージングアプリケーションプログラムインターフェイス (MAPI) のサブセットがサポートさ `CDocument` れています。 具体的に `CDocument` は、には、メールサポートがエンドユーザーのコンピューターに存在するかどうかを判断するメンバー関数があり、その場合は、標準のコマンド ID が ID_FILE_SEND_MAIL であるメール送信コマンドを有効にします。 このコマンドの MFC ハンドラー関数を使用すると、電子メールでドキュメントを送信できます。

> [!TIP]
> MFC では MAPI 関数セット全体がカプセル化されませんが、MFC プログラムから直接 Win32 API 関数を呼び出すことができるのと同じように、MAPI 関数を直接呼び出すことができます。

アプリケーションで [メールの送信] コマンドを指定するのは非常に簡単です。 MFC には、ドキュメント (つまり、から派生したオブジェクト) を添付ファイルとしてパッケージ化し、それをメールとして送信するための実装が用意されて `CDocument` います。 この添付ファイルは、ドキュメントの内容を電子メールメッセージに保存 (シリアル化) する、ファイルの保存コマンドに相当します。 この実装では、ユーザーのコンピューター上のメールクライアントでを呼び出して、メールアドレスを指定したり、件名やメッセージのテキストをメールメッセージに追加したりできるようにします。 ユーザーには、使い慣れたメールアプリケーションのユーザーインターフェイスが表示されます。 この機能は、との2つのメンバー関数によって提供され `CDocument` `OnFileSendMail` `OnUpdateFileSendMail` ます。

MAPI は、添付ファイルを送信するためにファイルを読み取る必要があります。 関数呼び出し中にアプリケーションがデータファイルを開いたままにする場合は、ファイルを `OnFileSendMail` 共有モードで開いて、複数のプロセスがファイルにアクセスできるようにする必要があります。

> [!NOTE]
> For クラスのオーバーライドバージョンは、 `OnFileSendMail` `COleDocument` 複合ドキュメントを正しく処理します。

#### <a name="to-implement-a-send-mail-command-with-mfc"></a>MFC でメール送信コマンドを実装するには

1. Visual C++ メニューエディターを使用して、コマンド ID が ID_FILE_SEND_MAIL メニュー項目を追加します。

   このコマンド ID は、AFXRES.H のフレームワークによって提供されます。始め. コマンドは任意のメニューに追加できますが、通常は [**ファイル**] メニューに追加されます。

1. ドキュメントのメッセージマップに次のコードを手動で追加します。

   [!code-cpp[NVC_MFCDocView#9](codesnippet/cpp/mapi-support-in-mfc_1.cpp)]

    > [!NOTE]
    >  このメッセージマップは、またはのいずれかから派生したドキュメントに対して機能し `CDocument` `COleDocument` ます。メッセージマップが派生ドキュメントクラスにある場合でも、どちらの場合も正しい基本クラスを取得します。

1. アプリケーションをビルドします。

メールサポートが利用可能な場合、MFC では、でメニュー項目を有効に `OnUpdateFileSendMail` し、その後でコマンドをで処理し `OnFileSendMail` ます。 メールサポートが利用できない場合は、ユーザーがメニュー項目を表示しないように、MFC によって自動的に削除されます。

> [!TIP]
> 前に説明したようにメッセージマップエントリを手動で追加するのではなく、クラス[クラスウィザード](reference/mfc-class-wizard.md)を使用して、メッセージを関数にマップできます。 詳細については、「[関数へのメッセージのマッピング](reference/mapping-messages-to-functions.md)」を参照してください。

関連情報については、「 [MAPI](mapi.md)の概要」を参照してください。

MAPI を有効にするメンバー関数の詳細については `CDocument` 、以下を参照してください。

- [CDocument:: OnFileSendMail](reference/cdocument-class.md#onfilesendmail)

- [CDocument:: OnUpdateFileSendMail](reference/cdocument-class.md#onupdatefilesendmail)

- [COleDocument:: OnFileSendMail](reference/coledocument-class.md#onfilesendmail)

## <a name="see-also"></a>関連項目

[MAPI](mapi.md)
