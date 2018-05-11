---
title: アクセラレータの種類 プロパティ |Microsoft ドキュメント
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
ms.openlocfilehash: cb1ba8f117fadab7cccb835ba8889d57bcc9f184
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="accelerator-type-property"></a>アクセラレータの [タイプ] プロパティ
アクセラレータ**型**プロパティは、アクセラレータ ID に関連付けられているショートカット キーの組み合わせが仮想キーの組み合わせまたは ASCII/ANSI キーの値かどうかを決定します。  
  
-   場合、**型**プロパティは**ASCII**、[修飾子](../windows/accelerator-modifier-property.md)なしにしかなれませんか、または alt キーを押し、CTRL キーを使用するアクセラレータを持つことができます (前のキーで指定された、^)。  
  
-   場合、**型**プロパティは**VIRTKEY**修飾子とキー値の任意の組み合わせが無効です。  
  
    > [!NOTE]
    >  アクセラレータ テーブルに値を入力し、ASCII または ANSI として扱われます値である場合は、テーブル内のエントリの種類と、ドロップダウン リストから選択 ASCII をクリックします。 ただし、使用する場合、 **キー タイピング登録**コマンド (**編集**メニュー) キーを指定する必要がありますを変更する、**型**プロパティ VIRTKEY から ASCII に*する前に*キー コードを入力します。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [アクセラレータのプロパティの設定](../windows/setting-accelerator-properties.md)   
 [アクセラレータ エディター](../windows/accelerator-editor.md)