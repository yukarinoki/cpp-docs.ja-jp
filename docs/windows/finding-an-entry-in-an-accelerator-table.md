---
title: アクセラレータ テーブル (C++) 内のエントリの検索 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- searching, in accelarator tables
- accelerator tables [C++], finding entries
ms.assetid: 98146b12-571e-48ea-a660-eb6b1834a79b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6fd8a4b6781008b80be1b0c8fd33bc7f1eece7f9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431321"
---
# <a name="finding-an-entry-in-an-accelerator-table"></a>アクセラレータ テーブルでのエントリの検索

### <a name="to-find-an-entry-in-an-open-accelerator-table"></a>開いているアクセラレータ テーブルでエントリを検索するには

1. アイコンをダブルクリックして、アクセラレータ テーブルを開く[リソース ビュー](../windows/resource-view-window.md)します。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. 列ヘッダーをクリックして、列の内容をアルファベット順に並べ替えます。 たとえば、をクリックして**ID**アクセラレータ テーブル内のすべての Id をアルファベット順に表示します。

これで、一覧に目を通しながらエントリを探すことができます。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[アクセラレータ テーブルの編集](../windows/editing-accelerator-tables.md)<br/>
[アクセラレータ エディター](../windows/accelerator-editor.md)