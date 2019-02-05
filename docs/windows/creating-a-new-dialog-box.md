---
title: ダイアログ ボックス (C++) の作成
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog
helpviewer_keywords:
- dialog boxes [C++], creating
- Dialog Editor [C++], creating dialog boxes
- modal dialog boxes [C++], logon screens
- logon screens
ms.assetid: 303de801-c4f8-42e1-b622-353f6423f688
ms.openlocfilehash: 928432000fb9a6347433b78b224e15f07ce810d2
ms.sourcegitcommit: 52c05e10b503e834c443ef11e7ca1987e332f876
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2019
ms.locfileid: "55742649"
---
# <a name="creating-a-dialog-box-c"></a>ダイアログ ボックス (C++) の作成

マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="to-create-a-new-dialog-box"></a>新しいダイアログ ボックスを作成するには

1. [リソース ビュー](../windows/resource-view-window.md)、.rc ファイルを右クリックし **リソースの追加**ショートカット メニューからです。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

1. **リソースの追加**ダイアログ ボックスで、**ダイアログ**で、**リソースの種類**し選択**新規**します。

   プラス記号の場合 (**+**) 横に表示されます、**ダイアログ**ダイアログ ボックスのテンプレートが使用できることを意味、リソースの種類。 テンプレートの一覧を展開し、テンプレートを選択して、選択、プラス記号を選択します。**新規**します。

   新しいダイアログ ボックスが開き、**ダイアログ**エディター。

   できます[の編集 ダイアログ ボックスのエディターで既存のダイアログ ボックスを開く](../windows/viewing-and-editing-resources-in-a-resource-editor.md)します。

## <a name="to-create-a-dialog-box-that-a-user-cant-exit"></a>ユーザーが終了できないダイアログ ボックスを作成するには

ユーザーが終了できない実行時のダイアログ ボックスを作成することができます。 この種のダイアログ ボックスはログオンの場合や、アプリケーションやドキュメントをロックする場合に便利です。

1. ダイアログ ボックスの **[プロパティ]** ウィンドウで、 **[システム メニュー]** プロパティを **[false]** に設定します。

   この設定は、ダイアログ ボックスのシステム メニューを無効にし、**閉じる**ボタンをクリックします。

1. ダイアログ ボックスのフォームで、 **[キャンセル]** ボタンと **[OK]** ボタンを削除します。

   ユーザーは、実行時に、これらの特性を持つモーダル ダイアログ ボックスを終了できません。

この種のダイアログ ボックスのテストを有効にする ダイアログ ボックスのテスト機能を検出ときに**Esc**が押されました。 (**Esc** VK_ESCAPE 仮想キーとも呼ばれます)。実行時の動作 ダイアログ ボックスの設計方法に関係なく、キーを押してテスト モードを終了できます**Esc**します。

> [!NOTE]
> MFC アプリケーションの場合にユーザーが終了できないダイアログ ボックスを作成する必要があります動作をオーバーライドする、既定の`OnOK`と`OnCancel`に関連付けられたボタンを削除する場合でもダイアログ ボックスはキーを押しても閉じることができますので**入力**または**Esc**します。

マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[方法: リソースを作成する](../windows/how-to-create-a-resource.md)<br/>
[リソース ファイル](../windows/resource-files-visual-studio.md)<br/>
[ダイアログ エディター](../windows/dialog-editor.md)