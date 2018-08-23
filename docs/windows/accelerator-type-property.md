---
title: アクセラレータの種類のプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Type property
- VIRTKEY
ms.assetid: 8c349bc4-e6ad-43fa-959e-f29168af35b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 59fae6d0809e32883d5d56e43e64525e23643d91
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602327"
---
# <a name="accelerator-type-property"></a>アクセラレータの [タイプ] プロパティ

アクセラレータ**型**プロパティは、アクセラレータ ID に関連付けられているショートカット キーの組み合わせが仮想キーの組み合わせまたは ASCII/ANSI キーの値がかどうかを決定します。

- 場合、**型**プロパティは、ASCII、[修飾子](../windows/accelerator-modifier-property.md)場合のみ`None`または`Alt`、またはアクセラレータを使用することができます、 **Ctrl** (で指定されたキー前のキーを`^`)。

- 場合、**型**プロパティは VIRTKEY を任意に組み合わせた`Modifier`と`Key`値が無効です。

   > [!NOTE]
   > アクセラレータ テーブルに値を入力して ASCII/ANSI をクリックすることとして扱う値を設定する場合、**型**ドロップダウン リストから ASCII を選択、テーブル内のエントリ。 ただし、使用する場合、 **キー タイピング登録**コマンド (**編集**メニュー) を指定する、 `Key`、変更する必要があります、**型**プロパティ VIRTKEY から ASCIIに*する前に*入力、`Key`コード。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[アクセラレータのプロパティの設定](../windows/setting-accelerator-properties.md)  
[アクセラレータ エディター](../windows/accelerator-editor.md)