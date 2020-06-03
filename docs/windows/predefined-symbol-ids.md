---
title: 定義済みのシンボル ID
ms.date: 02/14/2019
helpviewer_keywords:
- symbols [C++], predefined IDs
- predefined symbol IDs
ms.assetid: 91a5d610-1a04-47e8-b8a4-63ad650a90df
ms.openlocfilehash: 8f7fcba864f4e1a47d217d684b87c257503aeb13
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80215164"
---
# <a name="predefined-symbol-ids"></a>定義済みのシンボル ID

新しいプロジェクトを開始する時点で、ユーザーが使用できるように、プロジェクトの種類に応じていくつかのシンボル ID が事前に定義されています。 これらのシンボル ID は、MFC など、さまざまなライブラリとプロジェクトの種類をサポートします。 これらのシンボル ID は、アプリケーションに通常含まれている共通のタスクか、マウスやポインターなどのハードウェア アイテムのアクションを表します。

これらのシンボル ID は、リソースを使用する際に重要になります。 これらは、アクセラレータテーブルを編集するときに使用でき、その一部が既に仮想キーに関連付けられています。 また、[プロパティウィンドウ](/visualstudio/ide/reference/properties-window)を通じて使用することもできます。 任意の定義済みシンボル Id を新しいリソースに割り当てることができます。また、アクセラレータキーを割り当てることもできます。シンボル ID に関連付けられている機能は、自動的にそのキーの組み合わせと関連付けられます。

ライブラリには、プロジェクトの一部として表示される定義済みのシンボルがあります。

- [ATL の定義済みシンボル](../windows/atl-predefined-symbols.md)

- [MFC の定義済みシンボル](../windows/mfc-predefined-symbols.md)

- [Win32 の定義済みシンボル](../windows/win32-predefined-symbols.md)

> [!NOTE]
> 定義済みのシンボルは、常に読み取り専用です。

## <a name="requirements"></a>必要条件

Win32、MFC、または ATL

## <a name="see-also"></a>参照

[リソース識別子 (シンボル)](../windows/symbols-resource-identifiers.md)<br/>
[方法: シンボルを作成する](../windows/creating-new-symbols.md)<br/>
[方法: シンボルを管理する](../windows/changing-a-symbol-or-symbol-name-id.md)<br/>
