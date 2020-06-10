---
title: ON_UPDATE_COMMAND_UI マクロ
ms.date: 09/06/2019
f1_keywords:
- ON_UPDATE_COMMAND_UI
helpviewer_keywords:
- ON_UPDATE_COMMAND_UI macro [MFC]
- update handlers [MFC]
- command-handler macros
- updating user-interface objects [MFC]
ms.assetid: 3e72b50f-4119-4c82-81cf-6e09b132de05
ms.openlocfilehash: ba5a48fabb9142c080e688e189e0983ad5ba2eda
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624056"
---
# <a name="on_update_command_ui-macro"></a>ON_UPDATE_COMMAND_UI マクロ

コマンドターゲットオブジェクトのコマンド更新ハンドラーにユーザーインターフェイスオブジェクトを接続するには、**クラスビュー**を開き、ハンドラーを追加するクラスを右クリックして、[**クラスウィザード**] を選択します。 左側の一覧でユーザーインターフェイスオブジェクトの ID を探し、右側のウィンドウで [ **UPDATE_COMMAND_UI** ] を選択し、[**ハンドラーの追加**] をクリックします。 これにより、クラスにハンドラー関数が作成され、メッセージマップに適切なエントリが追加されます。 詳細については、「[関数へのメッセージのマッピング](reference/mapping-messages-to-functions.md)」を参照してください。 **メッセージ**ウィンドウで、処理する追加のメッセージを指定できます。

たとえば、プログラムの [編集] メニューの [すべてクリア] コマンドを更新するには、**クラスウィザード**を使用して、選択したクラスのメッセージマップエントリ、クラス宣言で呼び出されたコマンド更新ハンドラーの関数宣言、 `OnUpdateEditClearAll` およびクラスの実装ファイル内の空の関数テンプレートを追加します。 関数プロトタイプは次のようになります。

[!code-cpp[NVC_MFCDocView#2](codesnippet/cpp/on-update-command-ui-macro_1.h)]

すべてのハンドラーと同様に、関数宣言は**afx_msg**キーワードを示しています。 すべての更新ハンドラーと同様に、オブジェクトへのポインターである1つの引数を受け取り `CCmdUI` ます。

## <a name="see-also"></a>関連項目

[ユーザー インターフェイス オブジェクトの更新方法](how-to-update-user-interface-objects.md)
