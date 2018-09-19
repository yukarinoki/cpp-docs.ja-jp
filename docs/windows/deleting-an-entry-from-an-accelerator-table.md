---
title: アクセラレータ テーブル (C++) のエントリの削除 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], deleting entries
- keyboard shortcuts [C++], deleting entry from accelerator table
ms.assetid: cc9cd499-dc04-4fe6-9393-a3e471e115a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 747e0db32a73a277ef26e18e787e3e5a31f69578
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315120"
---
# <a name="deleting-an-entry-from-an-accelerator-table-c"></a>アクセラレータ テーブル (C++) のエントリの削除

### <a name="to-delete-an-entry-from-an-accelerator-table"></a>アクセラレータ テーブルのエントリを削除するには

1. アイコンをダブルクリックして、アクセラレータ テーブルを開く[リソース ビュー](../windows/resource-view-window.md)します。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. 削除するエントリを選択します (を押しながら、 **Ctrl**または**Shift**を複数のエントリを選択しますクリックしてキー。)。

3. 右クリックし、**削除**、ショートカット メニューから (または選択**削除**から、**編集**メニュー)。

\- または -

- キーを押して、**削除**キー。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[アクセラレータ テーブルの編集](../windows/editing-accelerator-tables.md)  
[アクセラレータ エディター](../windows/accelerator-editor.md)