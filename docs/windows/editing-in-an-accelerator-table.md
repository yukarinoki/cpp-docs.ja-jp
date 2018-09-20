---
title: アクセラレータ テーブル (C++) での編集 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], editing
- keyboard shortcuts [C++], editing in an accelerator table
ms.assetid: 545b650b-4f26-4b20-8431-d942548443bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 57347b88fe7d54813e06cde6d5f4b3414e79f116
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46395811"
---
# <a name="editing-in-an-accelerator-table-c"></a>アクセラレータ テーブル (C++) での編集

### <a name="to-edit-in-an-accelerator-table"></a>アクセラレータ テーブルで編集するには

1. アイコンをダブルクリックして、アクセラレータ テーブルを開く[リソース ビュー](../windows/resource-view-window.md)します。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. テーブル内のエントリを選択し、クリックしてインプレース編集をアクティブにします。

3. 変更するには、ドロップダウン コンボ ボックスから選択するか、インプレースで入力します。

   - [ID](id-property.md)でリストまたは入力して編集を選択します。

   - [修飾子](../windows/accelerator-modifier-property.md)を一覧から選択します。

   - [キー](../windows/accelerator-key-property.md)でリストまたは入力して編集を選択します。

   - [型](../windows/accelerator-type-property.md)、 **ASCII**または**VIRTKEY**一覧から。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[アクセラレータ テーブルの編集](../windows/editing-accelerator-tables.md)<br/>
[アクセラレータ エディター](../windows/accelerator-editor.md)