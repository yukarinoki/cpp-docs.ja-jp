---
title: リモートの Linux コンピューターへの接続 | Microsoft Docs
ms.custom: ''
ms.date: 11/06/2017
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: 5eeaa683-4e63-4c46-99ef-2d5f294040d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: dd7f73a01b3b0941144ff59a683a9e42467f5a18
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="connect-to-your-remote-linux-computer"></a>リモートの Linux コンピューターへの接続

ビルド時に、Linux コードはリモートの Linux コンピューターにコピーされ、Visual Studio で選択した設定に応じて、そのシステム上でコンパイルされます。  このリモート接続をセットアップするには、次のようにします。

1. 最初にプロジェクトをビルドするか、新しいエントリを手動で作成します。その場合、**[ツール]、[オプション]** の順に選択し、**[クロス プラットフォーム]、[接続マネージャー]** ノードの順に開き、**[追加]** ボタンをクリックします。

   ![接続マネージャー](media/settings_connectionmanager.png)

   いずれの場合も、**[Connect to Remote System]** (リモート システムへの接続) ウィンドウが表示されます。
   
   ![リモート システムへの接続](media/connect.png)

1. 次の情報を入力します。

   | 入力 | 説明
   | ----- | ---
   | **ホスト名**           | ターゲット デバイスの名前または IP アドレス
   | **ポート**                | SSH サービスが実行されているポート (通常は 22)
   | **ユーザー名**           | 認証するユーザー
   | **認証の種類** | パスワードと秘密キーの両方がサポートされます。
   | **パスワード**            | 入力したユーザー名のパスワード
   | **秘密キー ファイル**    | ssh 接続用に作成された秘密キー
   | **パスフレーズ**          | 上で選択した秘密キーで使用されるパスフレーズ

1. **[接続]** ボタンをクリックすると、リモート コンピューターへの接続が試行されます。  接続に失敗した場合は、変更する必要がある入力ボックスが赤色で示されます。

   ![接続マネージャーのエラー](media/settings_connectionmanagererror.png)