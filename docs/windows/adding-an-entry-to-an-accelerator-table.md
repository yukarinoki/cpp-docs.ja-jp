---
title: アクセラレータ テーブル (C++) へのエントリの追加 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], adding entries
- New Accelerator command
ms.assetid: 559c2415-8323-4339-9447-6966665f8288
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0e0017e0c4d5462ef985b70b44120ff20066f626
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391801"
---
# <a name="adding-an-entry-to-an-accelerator-table-c"></a>アクセラレータ テーブル (C++) へのエントリの追加

### <a name="to-add-an-entry-to-an-accelerator-table"></a>アクセラレータ テーブルにエントリを追加するには

1. C++ プロジェクトでのアイコンをダブルクリックして、アクセラレータ テーブルを開く[リソース ビュー](../windows/resource-view-window.md)します。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. アクセラレータ テーブル内で右クリックし、**新しいアクセラレータ**からショートカット メニューのまたはテーブルの下部にある空の行エントリをクリックします。

3. 選択、 [ID](id-property.md) ID のドロップダウン リストからボックスまたは新しい ID を入力、 **ID**ボックス。

4. 型、[キー](../windows/accelerator-key-property.md)アクセラレータまたは右クリックとして使用する**キー タイピング登録**キーの組み合わせを設定するショートカット メニュー (、 **キー タイピング登録**コマンドは、使用可能な**編集**メニュー)。

5. 変更、[修飾子](../windows/accelerator-modifier-property.md)と[型](../windows/accelerator-type-property.md)、必要な場合。

6. **Enter** キーを押します。

   > [!NOTE]
   > 定義するすべてのアクセラレータが一意であることを確認します。 たとえば、同じ ID に割り当てられているいくつかのキーの組み合わせがあることができます**Ctrl** + **P**と**F8**どちらも ID_PRINT に割り当てる割り当てすることができます。 ただし、1 つ以上の ID は、うまく機能しませんなどに割り当てられているキーの組み合わせを持つ**Ctrl** + **Z** ID_SPELL_CHECK と ID_THESAURUS の両方に割り当てられます。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[アクセラレータ テーブルの編集](../windows/editing-accelerator-tables.md)<br/>
[アクセラレータ エディター](../windows/accelerator-editor.md)