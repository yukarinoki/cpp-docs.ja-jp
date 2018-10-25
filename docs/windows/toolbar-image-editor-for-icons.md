---
title: ツールバー (アイコン用イメージ エディターを C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
dev_langs:
- C++
helpviewer_keywords:
- Graphics toolbar
- Image editor [C++], toolbar
- Image editor [C++], Option selector
- Properties window
- Option selector, Image editor
ms.assetid: a0af4209-6273-4106-a7c1-0edecc9b5755
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ed6639bdf86a54689834c6eda03a3b6ec4dd171d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063849"
---
# <a name="toolbar-c-image-editor-for-icons"></a>ツールバー (アイコン用イメージ エディターを C++)

**イメージ エディター**ツールバーには、描画、描画、テキストを入力する、消去、およびビューを操作するためのツールが含まれています。 オプション セレクターで、各ツールを使用するためのオプションを選択することができますも含まれています。 たとえば、さまざまなブラシの幅、拡大率、および線のスタイルから選択することができます。

> [!NOTE]
> 使用できるすべてのツール、**イメージ エディター**ツールバーも使用できます、**イメージ**メニュー (で、**ツール**コマンド)。

![イメージ エディターのツールバー](../mfc/media/vcimageeditortoolbar.gif "vcImageEditorToolbar")イメージ エディターのツールバー

使用する、**イメージ エディター**ツールバーと**オプション**セレクターで、[ツール] をクリックまたはするオプションします。

> [!TIP]
> ツール バー ボタンの上にカーソルを置くとツール ヒントが表示されます。 これらのヒントは、各ボタンの機能を識別するのに役立ちます。

**オプション**セレクター行やブラシなどの幅を指定することができます。上のアイコン、**オプション**セレクター ボタンが選択したツールを変更します。

![描画&#45;イメージ エディターのツールバーの図形セレクター](../mfc/media/vcimageeditortoolbaroptionselector.gif "vcImageEditorToolbarOptionSelector")イメージ エディターのツールバーでオプション セレクター

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

なし

## <a name="see-also"></a>関連項目

[表示するか、ツールバーを非表示](displaying-or-hiding-the-toolbar-image-editor-for-icons.md)<br/>
[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[アイコン用イメージ エディター](../windows/image-editor-for-icons.md)