---
title: アクセラレータ テーブル (C++) での編集
ms.date: 11/04/2016
helpviewer_keywords:
- accelerator tables [C++], editing
- keyboard shortcuts [C++], editing in an accelerator table
ms.assetid: 545b650b-4f26-4b20-8431-d942548443bd
ms.openlocfilehash: 3955a74f9387c5f89d4217436e16e76b53bc3f6a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463002"
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

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[アクセラレータ テーブルの編集](../windows/editing-accelerator-tables.md)<br/>
[アクセラレータ エディター](../windows/accelerator-editor.md)