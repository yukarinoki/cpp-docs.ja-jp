---
title: 1 つの形式からイメージを変換するもう 1 つ (アイコン用イメージ エディター) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- images [C++], stand-alone editing
- Image editor [C++], converting image formats
- graphics [C++], converting formats
- images [C++], converting formats
ms.assetid: 0409c2bd-3bd8-4d72-9c71-c683b6cf51be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b34b0a55f079962860bb0d9055f19780273d267
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406387"
---
# <a name="converting-an-image-from-one-format-to-another-image-editor-for-icons"></a>イメージの形式変換 (アイコン用イメージ エディター)

Gif 形式や JPEG イメージを開くことができます、**イメージ**エディター ビットマップとして保存します。 また、ビットマップ ファイルを開くし、gif 形式や JPEG として保存できます。 使用するイメージで開発環境で編集するためのプロジェクトの一部必要はありません (を参照してください[スタンドアロン画像編集](../windows/editing-an-image-outside-of-a-project-image-editor-for-icons.md))。

### <a name="to-convert-an-image-from-one-format-to-another"></a>イメージを別の 1 つの形式に変換するには

1. 内のイメージを開く、**イメージ**エディター。

2. **ファイル**] メニューの [選択**保存*filename*として**します。

3. **ファイルに名前を付けて** ダイアログ ボックスで、**ファイル名**ボックスに、ファイル名と必要な形式を示す拡張子を入力します。

4. **[保存]** をクリックします。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

なし

## <a name="see-also"></a>関連項目

[グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[アイコン用イメージ エディター](../windows/image-editor-for-icons.md)