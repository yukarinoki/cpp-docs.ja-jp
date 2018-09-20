---
title: コントロール グループの配置 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], aligning
ms.assetid: a4f49a73-4a17-44b3-8568-aa35f646b5cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c791f2951eb7ac9947d48b563bde624bc3b7979f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393582"
---
# <a name="aligning-groups-of-controls"></a>コントロール グループの配置

次の手順では、コントロールのグループを配置する方法を示します。

### <a name="to-align-groups-of-controls"></a>コントロールのグループを配置するには

1. [コントロールを選択する](../windows/selecting-multiple-controls.md)を配置します。 主要なコントロールを最初にするコントロールを選択することを確認するまたは配置を実行しているか、コマンドのサイズを変更する前に、主要なコントロールに設定します。

   コントロールのグループの最後の位置は、主要なコントロールの位置に依存します。 主要なコントロールを選択する方法の詳細については、次を参照してください。[主要なコントロールを指定する](../windows/specifying-the-dominant-control.md)します。

2. **形式**] メニューの [選択**Align**、以下の配置のいずれかを選択。

   - `Lefts`: 選択したコントロールの左端に揃えて配置します。

   - `Centers`: 選択したコントロールを水平方向の中心点を揃えて配置します。

   - `Rights`: 選択したコントロールの右端に揃えて配置します。

   - `Tops`: 選択したコントロールをそれらの上端に沿って配置します。

   - `Middles`: 選択したコントロールを垂直方向中央の点に配置します。

   - `Bottoms`: 選択したコントロールの下端に揃えて配置します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロールの配置](../windows/arrangement-of-controls-on-dialog-boxes.md)<br/>
[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)<br/>
[コントロール](../mfc/controls-mfc.md)