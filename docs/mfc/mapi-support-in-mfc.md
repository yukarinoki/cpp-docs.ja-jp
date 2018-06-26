---
title: MFC での MAPI サポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, MAPI support
- MAPI support in MFC
- CDocument class [MFC], and MAPI
- OnUpdateFileSendMail method [MFC]
- MAPI, MFC
- OnFileSendMail method [MFC]
ms.assetid: cafbecb1-0427-4077-b4b8-159bae5b49b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 301e15b11b05f9ccbeaee63aead486f1cc6c405c
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931903"
---
# <a name="mapi-support-in-mfc"></a>MFC での MAPI サポート
MFC での Microsoft メッセージング アプリケーション プログラム インターフェイス (MAPI) クラスのサブセットのサポートに提供`CDocument`です。 具体的には、`CDocument`メール サポートがエンドユーザーのコンピューター上に存在するかどうかを決定するメンバー関数があり、その場合は、標準コマンド ID が判定メール送信コマンドを有効にします。 このコマンドの MFC ハンドラー関数により、ユーザーに電子メールでドキュメントを送信します。  
  
> [!TIP]
>  MFC は、全体の MAPI 関数のセットをカプセル化しないができますも呼び出すことが MAPI 関数直接、MFC プログラムから直接 Win32 API 関数を呼び出すことができます。  
  
 アプリケーションでのコマンドはメールの送信を提供することは非常に簡単です。 MFC はドキュメントをパッケージ化する実装を提供 (つまり、 `CDocument`-派生オブジェクト) の添付ファイルとしてとメールとして送信します。 この添付ファイルは保存するファイルの保存のコマンドに相当 (シリアル化) メール メッセージに、ドキュメントの内容。 メールの宛先と件名とメッセージのテキスト メッセージを追加する機会をユーザーに提供するユーザーのコンピューター上のメール クライアントと、この実装を呼び出します。 ユーザーが使い慣れたメール アプリケーションのユーザー インターフェイスを参照してください。 この機能は、2 つのによって提供される`CDocument`メンバー関数:`OnFileSendMail`と`OnUpdateFileSendMail`です。  
  
 MAPI は、添付ファイルを送信するファイルを読み取る必要があります。 アプリケーションが保持、データ ファイルの中に開いている場合、`OnFileSendMail`関数呼び出しに複数のプロセス ファイルへのアクセス許可を共有モードで開かれるファイルが必要があります。  
  
> [!NOTE]
>  オーバーライド元のバージョンの`OnFileSendMail`クラス`COleDocument`正しくハンドル複合ドキュメント。  
  
#### <a name="to-implement-a-send-mail-command-with-mfc"></a>MFC でのメール送信コマンドを実装するには  
  
1.  コマンド ID が判定メニュー項目を追加するのにには、Visual C メニュー エディターを使用します。  
  
     このコマンド ID は、コマによって提供されます。H. 任意のメニューにコマンドを追加することができますにも追加は、通常、**ファイル**メニュー。  
  
2.  ドキュメントのメッセージ マップを次を手動で追加するには。  
  
     [!code-cpp[NVC_MFCDocView#9](../mfc/codesnippet/cpp/mapi-support-in-mfc_1.cpp)]  
  
    > [!NOTE]
    >  このメッセージ マップのいずれかから派生したドキュメントの動作`CDocument`または`COleDocument`— 場合でも、メッセージ マップは、ドキュメントの派生クラスではどちらの場合、正しい基本クラスを選択します。  
  
3.  アプリケーションをビルドします。  
  
 メールのサポートが利用可能な場合は、MFC を有効にしてメニュー項目`OnUpdateFileSendMail`し、その後でコマンドを処理`OnFileSendMail`です。 このオプションをメール サポートが使用できない場合、ユーザーは表示されませんように自動的に、MFC は、メニュー項目を削除します。  
  
> [!TIP]
>  前述したようにメッセージ マップ エントリを手動で追加するではなくには、クラスのプロパティ ウィンドウを使用して関数にメッセージをマップすることができます。 詳細については、次を参照してください。[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md)です。  
  
 関連情報については、次を参照してください。、 [MAPI](../mfc/mapi.md)の概要です。  
  
 詳細については、 `CDocument` MAPI できるメンバー関数を参照してください。  
  
-   [CDocument::OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)  
  
-   [CDocument::OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)  
  
-   [COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)  
  
## <a name="see-also"></a>関連項目  
 [MAPI](../mfc/mapi.md)

