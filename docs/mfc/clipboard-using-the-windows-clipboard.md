---
description: '詳細については、「クリップボード: Windows クリップボードの使用」を参照してください。'
title: 'クリップボード : Windows クリップボードの使用方法'
ms.date: 11/04/2016
helpviewer_keywords:
- Clipboard commands
- Cut/Copy and Paste command handler functions [MFC]
- handler functions, Cut/Copy and Paste commands
- Clipboard [MFC], commands
- commands [MFC], implementing Edit
- Clipboard commands [MFC], implementing
- Windows Clipboard [MFC]
- Clipboard [MFC], Windows Clipboard API
ms.assetid: 24415b42-9301-4a70-b69a-44c97918319f
ms.openlocfilehash: 1c89c8888f7e3ffb81705ee146c00917a7763323
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338420"
---
# <a name="clipboard-using-the-windows-clipboard"></a>クリップボード : Windows クリップボードの使用方法

このトピックでは、MFC アプリケーション内で標準の Windows クリップボード API を使用する方法について説明します。

Windows のほとんどのアプリケーションでは、Windows クリップボードへのデータの切り取りまたはコピーと、クリップボードからのデータの貼り付けがサポートされています。 クリップボードのデータ形式は、アプリケーションによって異なります。 フレームワークは、限られた数のクラスに対して、限られた数のクリップボード形式のみをサポートしています。 通常は、クリップボード関連のコマンド (切り取り、コピー、貼り付け) を、ビューの [編集] メニューに実装します。 クラスライブラリでは、これらのコマンドのコマンド Id ( **ID_EDIT_CUT**、 **ID_EDIT_COPY**、および **ID_EDIT_PASTE** を定義します。 メッセージ行のプロンプトも定義されています。

[フレームワークのメッセージとコマンド](messages-and-commands-in-the-framework.md) では、メニューコマンドをハンドラー関数にマップすることによって、アプリケーションでメニューコマンドを処理する方法について説明します。 アプリケーションで、[編集] メニューのクリップボードコマンドのハンドラー関数が定義されていない限り、無効のままになります。 切り取りおよびコピーコマンドのハンドラー関数を記述するには、アプリケーションで選択を実装します。 貼り付けコマンドのハンドラー関数を記述するには、クリップボードに対してクエリを実行し、アプリケーションが受け入れられる形式のデータが含まれているかどうかを確認します。 たとえば、Copy コマンドを有効にするには、次のようなハンドラーを記述します。

[!code-cpp[NVC_MFCListView#2](../atl/reference/codesnippet/cpp/clipboard-using-the-windows-clipboard_1.cpp)]

切り取り、コピー、貼り付けの各コマンドは、特定のコンテキストでのみ意味があります。 切り取りコマンドとコピーコマンドは、何かが選択されている場合にのみ有効にし、クリップボードに何かがある場合にのみ貼り付けコマンドを有効にする必要があります。 コンテキストに応じてこれらのコマンドを有効または無効にする更新ハンドラー関数を定義することで、この動作を提供できます。 詳細については、「 [How To Update User-Interface Objects](how-to-update-user-interface-objects.md)」を参照してください。

Microsoft Foundation Class ライブラリには、およびクラスを使用したテキスト編集のためのクリップボードサポートが用意されて `CEdit` `CEditView` います。 Ole クラスでは、OLE アイテムに関連するクリップボード操作の実装も簡略化されます。 OLE クラスの詳細については、「 [クリップボード: Ole クリップボード機構の使用](clipboard-using-the-ole-clipboard-mechanism.md)」を参照してください。

他の編集メニューコマンド (元に戻す (**ID_EDIT_UNDO**) ややり直し (**ID_EDIT_REDO**) など) を実装することもお勧めします。 アプリケーションでこれらのコマンドがサポートされていない場合は、Visual C++ リソースエディターを使用してリソースファイルから簡単に削除できます。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [データのコピーと貼り付け](clipboard-copying-and-pasting-data.md)

- [OLE クリップボード機構の使用](clipboard-using-the-ole-clipboard-mechanism.md)

## <a name="see-also"></a>関連項目

[クリップボード](clipboard.md)
