---
title: 不要になった関数に、ダイアログ ボックス コントロールをダイアログ ボックスに追加すると、|Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], troubleshooting
- common controls, troubleshooting
- troubleshooting controls
- dialog boxes, troubleshooting
- dialog box controls, troubleshooting
- InitCommonControls
ms.assetid: b2dd4574-ea59-4343-8d65-b387cead5da6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b10c24955e74d08ab570b5b694628f42bb394268
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function"></a>コントロールを追加してもダイアログ ボックスに表示されない
ダイアログ ボックスに、コモン コントロールまたはリッチ エディット コントロールを追加すると、これは表示されません ダイアログ ボックスをテストするとダイアログ ボックス自体は表示されません。  
  
 **問題の例**  
  
1.  Windows アプリケーション (コンソール アプリケーションではなく) を作成するようにアプリケーションの設定を変更する、Win32 プロジェクトを作成します。  
  
2.  [リソース ビュー](../windows/resource-view-window.md)、.rc ファイルをダブルクリックします。  
  
3.  ダイアログ オプションでダブルクリックして、**に関する**ボックス。  
  
4.  追加、 **IP アドレス コントロール** ダイアログ ボックスにします。  
  
5.  保存と**すべてリビルド**です。  
  
6.  プログラムを実行します。  
  
7.  ダイアログ ボックスの **[ヘルプ]** メニューのをクリックして、**に関する**コマンド以外のダイアログ ボックスが表示されます。  
  
 **原因**  
  
 現時点では、ダイアログ エディターが自動的に追加されませんコードをプロジェクトにリッチ エディット コントロールをダイアログ ボックスまたはドラッグ アンド ドロップ、次の一般的なコントロールするときにします。 また、Visual Studio の管轄エラーまたは警告がこの問題が発生したとき。 コントロールのコードを手動で追加する必要があります。  
  
||||  
|-|-|-|  
|スライダー コントロール|ツリー コントロール|Date Time Picker|  
|スピン コントロール|タブ コントロール|月間予定表|  
|プログレス コントロール|アニメーション コントロール|IP アドレスの管理|  
|ホット キー|リッチ エディット コントロール|拡張コンボ ボックス|  
|リスト コントロール|リッチ エディット 2.0 コントロール|カスタム コントロール|  
  
## <a name="the-fix-for-common-controls"></a>コモン コントロールの修正方法  
 コモン コントロール ダイアログ ボックスを使用するために呼び出す必要がある[InitCommonControlsEx](http://msdn.microsoft.com/library/windows/desktop/bb775697)または**AFXInitCommonControls**  ダイアログ ボックスを作成する前にします。  
  
## <a name="the-fix-for-richedit-controls"></a>リッチ エディット コントロールの修正方法  
 呼び出す必要があります**LoadLibrary**リッチ エディット コントロールのです。 詳細については、次を参照してください。 [MFC での RichEdit 1.0 コントロールの使用](../windows/using-the-richedit-1-0-control-with-mfc.md)、[リッチのエディット コントロールについて](http://msdn.microsoft.com/library/windows/desktop/bb787873)で、 [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]、および[リッチ エディット コントロールの概要](../mfc/overview-of-the-rich-edit-control.md)です。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ エディターのトラブルシューティング](../windows/troubleshooting-the-dialog-editor.md)   
 [ダイアログ エディター](../windows/dialog-editor.md)

