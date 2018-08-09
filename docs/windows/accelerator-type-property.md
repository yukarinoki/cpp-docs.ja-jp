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
ms.openlocfilehash: da825a4f2052f05b24ff724d709c7c8a4b6a3db3
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645686"
---
# <a name="accelerator-type-property"></a>アクセラレータの [タイプ] プロパティ
アクセラレータ**型**プロパティは、アクセラレータ ID に関連付けられているショートカット キーの組み合わせが仮想キーの組み合わせまたは ASCII/ANSI キーの値がかどうかを決定します。  
  
-   場合、**型**プロパティは、ASCII、[修飾子](../windows/accelerator-modifier-property.md)場合のみ`None`または`Alt`、またはアクセラレータを使用することができます、 **Ctrl** (で指定されたキー前のキーを`^`)。  
  
-   場合、**型**プロパティは VIRTKEY を任意に組み合わせた`Modifier`と`Key`値が無効です。  
  
    > [!NOTE]
    >  アクセラレータ テーブルに値を入力して ASCII/ANSI をクリックすることとして扱う値を設定する場合、**型**ドロップダウン リストから ASCII を選択、テーブル内のエントリ。 ただし、使用する場合、 **キー タイピング登録**コマンド (**編集**メニュー) を指定する、 `Key`、変更する必要があります、**型**プロパティ VIRTKEY から ASCIIに*する前に*入力、`Key`コード。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [アクセラレータのプロパティの設定](../windows/setting-accelerator-properties.md)   
 [アクセラレータ エディター](../windows/accelerator-editor.md)