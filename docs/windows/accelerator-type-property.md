---
title: アクセラレータの種類のプロパティ (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- Type property
- VIRTKEY
ms.assetid: 8c349bc4-e6ad-43fa-959e-f29168af35b8
ms.openlocfilehash: 00699f31b821aa508feec9ffe062d768f27ee5a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475586"
---
# <a name="accelerator-type-property-c"></a>アクセラレータの種類のプロパティ (C++)

アクセラレータ**型**プロパティは、アクセラレータ ID に関連付けられているショートカット キーの組み合わせが仮想キーの組み合わせまたは ASCII/ANSI キーの値がかどうかを決定します。

- 場合、**型**プロパティは、ASCII、[修飾子](../windows/accelerator-modifier-property.md)場合のみ`None`または`Alt`、またはアクセラレータを使用することができます、 **Ctrl** (で指定されたキー前のキーを`^`)。

- 場合、**型**プロパティは VIRTKEY を任意に組み合わせた`Modifier`と`Key`値が無効です。

   > [!NOTE]
   > アクセラレータ テーブルに値を入力して ASCII/ANSI をクリックすることとして扱う値を設定する場合、**型**ドロップダウン リストから ASCII を選択、テーブル内のエントリ。 ただし、使用する場合、 **キー タイピング登録**コマンド (**編集**メニュー) を指定する、 `Key`、変更する必要があります、**型**プロパティ VIRTKEY から ASCIIに*する前に*入力、`Key`コード。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[アクセラレータのプロパティの設定](../windows/setting-accelerator-properties.md)<br/>
[アクセラレータ エディター](../windows/accelerator-editor.md)