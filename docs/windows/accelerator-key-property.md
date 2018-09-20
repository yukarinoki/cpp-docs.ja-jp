---
title: アクセラレータ キー プロパティ (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Key property
ms.assetid: d1570cd9-b414-4cd6-96bd-47c38281eaca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e0594e5b9e2d092330664546cbd05ccfb0060c42
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428968"
---
# <a name="accelerator-key-property-c"></a>アクセラレータ キー プロパティ (C++)

以下は、アクセラレータ テーブル内のキー プロパティに有効なエントリです。

- 0 ~ 255 の 10 進形式の範囲の整数。 値は、値が ASCII または ANSI として次のように扱われるかどうかを決定します。

   - 1 桁の数字は、常に、ASCII または ANSI の値ではなく、対応するキーとして解釈されます。

   - 1 ~ 26、ゼロが付く場合からの値として解釈されます ^ A ~ ^ Z で押されたときに、アルファベットの文字の ASCII 値を表す、 **Ctrl**キーが押し続けられます。

   - 27 ~ 32 の値は常に、3 桁の 10 進値 027 ~ 032 として解釈されます。

   - 前に 0 がまたはいない、ANSI 値として解釈されるかどうか、033 ~ 255 の値します。

- 1 つのキーボード文字。 A ~ Z の大文字または数字 0 - 9 は、ASCII または仮想キー値のいずれかを指定できます。その他の任意の文字には ASCII のみです。

- A ~ Z の範囲内の 1 つのキーボード文字 (大文字のみ)、キャレット (^) に続く (たとえば、^ C)。 これと一緒に押したときに、キーの ASCII 値を入力、 **Ctrl**キーが押し続けられます。

   > [!NOTE]
   > ASCII 値を入力するには、修飾子プロパティのオプションが制限されています。 使用するため利用可能な唯一のコントロール キーは、 **Alt**キー。

- 有効な仮想キー識別子。 アクセラレータ テーブルで、ドロップダウン リスト キーのボックスには、標準の仮想キー識別子の一覧が含まれています。

   > [!TIP]
   > アクセラレータ キーを定義する別の方法は、エントリ、または複数のアクセラレータ テーブル エントリを右クリックし、選択する**キー タイピング登録**ショートカット メニューからのキーまたはキーの組み合わせのいずれか、キーボードのキーを押します。 **キー タイピング登録**コマンドが表示されます、**編集**メニュー。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[アクセラレータのプロパティの設定](../windows/setting-accelerator-properties.md)<br/>
[アクセラレータ テーブルでのエントリの編集](../windows/editing-in-an-accelerator-table.md)<br/>
[アクセラレータ エディター](../windows/accelerator-editor.md)