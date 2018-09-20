---
title: 移動またはアクセラレータ テーブル エントリをコピーする別のリソース スクリプト ファイル (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], copying entries
- rc files [C++], moving an accelerator table entry
- .rc files [C++], moving accelerator table entries
- accelerator tables [C++], moving entries
ms.assetid: 7b4dc149-c972-4ab2-8477-76c52b6feb5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0d3f75ef8c2820c227716e3208ff2cded54d1fd7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414733"
---
# <a name="moving-or-copying-an-accelerator-table-entry-to-another-resource-script-file-c"></a>移動またはアクセラレータ テーブル エントリをコピーする別のリソース スクリプト ファイル (C++)

### <a name="to-move-or-copy-an-accelerator-table-entry-to-another-resource-script-file"></a>アクセラレータ テーブルのエントリを別のリソース スクリプト ファイルに移動またはコピーするには

1. 両方のリソース スクリプト ファイルでアクセラレータ テーブルを開きます。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. 移動するエントリを選択します。

3. **編集**] メニューの [選択**コピー**または**切り取り**します。

4. 移動先またはコピー先のリソース スクリプト ファイルでエントリを選択します。

5. **編集**] メニューの [選択**貼り付け**します。

   > [!NOTE]
   > コピーと貼り付けのショートカット キーも使用できます。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[アクセラレータ テーブルの編集](../windows/editing-accelerator-tables.md)<br/>
[アクセラレータ エディター](../windows/accelerator-editor.md)