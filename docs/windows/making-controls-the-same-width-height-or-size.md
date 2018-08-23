---
title: 同じ幅、高さ、またはサイズのコントロールの作成 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Make Same Size command
- controls [C++], sizing
ms.assetid: 94b50613-67e2-497b-a2b6-6d98dccfd345
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5077d2dcd426182495cc7a414aca7ca411d1fa60
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605377"
---
# <a name="making-controls-the-same-width-height-or-size"></a>複数のコントロールに対する同一の幅、高さ、またはサイズの設定

主要なコントロールのサイズに基づいてコントロールのグループのサイズを変更することができます。 できます[キャプション テキストのサイズに基づき、コントロールのサイズを変更](../windows/sizing-individual-controls.md)します。

### <a name="to-make-controls-the-same-width-height-or-size"></a>同じ幅、高さ、またはサイズを制御するには

1. [コントロールを選択する](../windows/selecting-multiple-controls.md)サイズを変更します。

   シリーズの最初に選択コントロールは、主要なコントロールです。 グループ内のコントロールの最終的なサイズは、主要なコントロールのサイズによって異なります。 主要なコントロールを選択する方法の詳細については、次を参照してください。[主要なコントロールを指定する](../windows/specifying-the-dominant-control.md)します。

2. **形式**] メニューの [選択**同じサイズに揃える**、次のコマンドのいずれかを選択します。

   - **両方とも**

   - **Height**

   - **Width**

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)  
[コントロール](../mfc/controls-mfc.md)