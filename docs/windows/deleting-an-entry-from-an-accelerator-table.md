---
title: アクセラレータ テーブルのエントリの削除 |Microsoft Docs
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
ms.openlocfilehash: 0c191a2e37e4fe99c12486270c34a558cf4e8455
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605408"
---
# <a name="deleting-an-entry-from-an-accelerator-table"></a>アクセラレータ テーブルのエントリの削除

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