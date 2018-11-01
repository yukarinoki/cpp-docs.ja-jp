---
title: 水平スクロール バーの幅の設定
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [C++], scroll bar width
- CListBox::SetHorizontalExtent
- controls [C++], scroll bar
- scroll bars [C++], displaying in controls
- horizontal scroll bar width
- CListBox class, scroll bar width
- scroll bars [C++], width
ms.assetid: 51dad141-aa0b-46a3-a82c-46b80d603d94
ms.openlocfilehash: 393571b79d27485e840d150549208c899e8ed1d2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625954"
---
# <a name="setting-the-width-of-a-horizontal-scroll-bar"></a>水平スクロール バーの幅の設定

MFC クラスを使用してダイアログ ボックスに水平スクロール バーを使用して、リスト ボックスを追加すると、スクロール バーは、アプリケーションでは自動的に表示されません。

### <a name="to-make-the-scroll-bar-appear"></a>スクロール バーの表示にする

1. 最も幅の広い要素の最大の幅を呼び出すことによって設定[CListBox::SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent)コードにします。

   この値を設定せず、スクロール バーは表示されません、でも、リスト ボックス内の項目は、ボックスよりも広い場合。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

MFC

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)<br/>
[コントロール](../mfc/controls-mfc.md)