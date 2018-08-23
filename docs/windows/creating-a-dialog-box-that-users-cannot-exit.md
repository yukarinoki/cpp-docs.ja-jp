---
title: ユーザーに終了できないダイアログ ボックスの作成 |Microsoft Docs
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
ms.openlocfilehash: cd3e68d89ce0a2ece83876b6afcd6aa09e59ed93
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598221"
---
# <a name="creating-a-dialog-box-that-users-cannot-exit"></a>ユーザーが終了できないダイアログ ボックスの作成

ユーザーには終了できない実行時ダイアログ ボックスを作成できます。 この種のダイアログ ボックスはログオンの場合や、アプリケーションやドキュメントをロックする場合に便利です。

### <a name="to-create-a-dialog-box-that-a-user-cannot-exit"></a>ユーザーには終了できないダイアログ ボックスを作成するには

1. ダイアログ ボックスの **[プロパティ]** ウィンドウで、 **[システム メニュー]** プロパティを **[false]** に設定します。

   これによって、ダイアログ ボックスのシステム メニューと **[閉じる]** ボタンが無効になります。

2. ダイアログ ボックスのフォームで、 **[キャンセル]** ボタンと **[OK]** ボタンを削除します。

   実行時にユーザーはこれらの特性を持つモーダル ダイアログ ボックスを終了できません。

この種のダイアログ ボックスのテストを有効にする ダイアログ ボックスのテスト機能を検出ときに**Esc**が押されました。 (**Esc** VK_ESCAPE 仮想キーとも呼ばれます)。実行時の動作 ダイアログ ボックスの設計方法に関係なく終了できますテスト モードでキーを押して**Esc**します。

> [!NOTE]
> MFC アプリケーションの場合にユーザーが終了できないダイアログ ボックスを作成する必要があります動作をオーバーライドする、既定の`OnOK`と`OnCancel`に関連付けられたボタンを削除する場合でもダイアログ ボックスはキーを押しても閉じることができますので**入力**または**Esc**します。

マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[方法: リソースを作成する](../windows/how-to-create-a-resource.md)  
[リソース ファイル](../windows/resource-files-visual-studio.md)  
[ダイアログ エディター](../windows/dialog-editor.md)