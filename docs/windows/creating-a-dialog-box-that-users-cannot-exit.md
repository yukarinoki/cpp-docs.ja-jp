---
title: ユーザーが終了できないダイアログ ボックスの作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes, creating
- modal dialog boxes, logon screens
- logon screens
ms.assetid: 54823c27-1658-4388-bd12-0a1ce8f3899e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fc04c9ccfb0fdc74e57142bf746681411bbba495
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="creating-a-dialog-box-that-users-cannot-exit"></a>ユーザーが終了できないダイアログ ボックスの作成
ユーザーには終了できない実行時ダイアログ ボックスを作成できます。 この種のダイアログ ボックスはログオンの場合や、アプリケーションやドキュメントをロックする場合に便利です。  
  
### <a name="to-create-a-dialog-box-that-a-user-cannot-exit"></a>ユーザーには終了できないダイアログ ボックスを作成するには  
  
1.  ダイアログ ボックスの **[プロパティ]** ウィンドウで、 **[システム メニュー]** プロパティを **[false]** に設定します。  
  
     これによって、ダイアログ ボックスのシステム メニューと **[閉じる]** ボタンが無効になります。  
  
2.  ダイアログ ボックスのフォームで、 **[キャンセル]** ボタンと **[OK]** ボタンを削除します。  
  
     実行時にユーザーはこれらの特性を持つモーダル ダイアログ ボックスを終了できません。  
  
 この種のダイアログ ボックスをテストできるようにするため、Esc キーが押されると、ダイアログ ボックスのテスト機能がそれを検出します。 (Esc キーは、VK_ESCAPE 仮想キーとも呼ばれます。)実行時にどのように動作するよう設計されているかに関わりなく、テスト モードで Esc キーを押すとダイアログ ボックスは終了します。  
  
> [!NOTE]
>  MFC アプリケーションの場合、ユーザーが終了できないダイアログ ボックスを作成するには、 `OnOK` ボタンと `OnCancel` の既定の動作をオーバーライドする必要があります。それらに関連付けられたボタンを削除しても、Enter キーまたは Esc キーを押せばダイアログ ボックスを終了できるためです。  
  
 マネージ プロジェクトにリソースを追加する方法については、次を参照してください。[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)です。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [方法: リソースの作成](../windows/how-to-create-a-resource.md)   
 [リソース ファイル (Visual Studio)](../windows/resource-files-visual-studio.md)   
 [ダイアログ エディター](../windows/dialog-editor.md)

