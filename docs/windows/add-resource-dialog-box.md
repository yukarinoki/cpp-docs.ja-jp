---
title: 追加のリソース ダイアログ ボックス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.insertresource
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], adding
- Add Resource dialog box
ms.assetid: e9fb6967-738f-47e8-ab58-728cf35b3af0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a48b99ad1d00fdcc184f6a3fadc772b32057f75d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601331"
---
# <a name="add-resource-dialog-box"></a>[リソースの追加] ダイアログ ボックス

このダイアログ ボックスは、C++ Windows デスクトップ アプリケーション プロジェクトにリソースを追加するときに使用します。

> [!NOTE]
> この情報は、ユニバーサル Windows プラットフォーム アプリでのリソースには適用されません。 詳細については、次を参照してください。[アプリのリソースとリソース管理システム](/windows/uwp/app-resources/)します。

### <a name="resource-type"></a>リソースの種類

作成するリソースの種類を指定します。

カーソルおよびダイアログ ボックスのリソースのカテゴリを展開すると、さらにリソースを表示できます。 ...\Microsoft Visual Studio でこれらのリソースがある`version`\VC\VCResourceTemplates\\< LCID\>\mfc.rct します。 .Rct ファイルを追加する、このディレクトリに配置する必要がありますまたはする必要がありますを指定する場合、[インクルード パス](../windows/how-to-specify-include-directories-for-resources.md)にします。 これらのファイルのリソースは、該当するカテゴリの第 2 レベルに表示されます。 追加できる .rct ファイル数については、事前に設定された制限はありません。

ツリー コントロールの最上位レベルに表示されるリソースは、Visual Studio に用意されている既定のリソースです。

### <a name="new"></a>新規作成

選択した型に基づくリソースの作成、**リソースの種類**ボックス。 リソースが適切なエディターで開きます。 たとえば、ダイアログ リソースを作成する場合で開きます、[ダイアログ エディター](../windows/dialog-editor.md)します。

### <a name="import"></a>インポート

表示されます、**インポート**できますを移動するリソースにする ダイアログ ボックスは、現在のプロジェクトにインポートします。 ビットマップ、アイコン、カーソル、HTML リソース ファイル、サウンド (.WAV) リソース ファイル、またはカスタム リソース ファイルをインポートできます。

### <a name="custom"></a>カスタム

開く、[新しいカスタム リソース ダイアログ ボックス](../windows/new-custom-resource-dialog-box.md)では、カスタム リソースを作成できます。 カスタム リソースを編集するには、バイナリ エディターを使用する必要があります。

## <a name="requirements"></a>要件

なし

## <a name="see-also"></a>関連項目

[方法: リソースを作成する](../windows/how-to-create-a-resource.md)