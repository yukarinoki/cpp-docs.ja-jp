---
title: 追加の終了に関する考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- quitting applications
- exiting applications
- programs [C++], terminating
ms.assetid: acbe2332-9d8a-4a58-a471-dd652a837384
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7f7b3c12c5889265ebb06e199c7f1e1e3cb440b4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034072"
---
# <a name="additional-termination-considerations"></a>終了に関するその他の考慮事項

使用して、C++ プログラムを終了する`exit`、**返す**、または`abort`します。 `atexit` 関数を使用して終了処理を追加できます。 次の各セクションでは、これらについて説明します。

## <a name="see-also"></a>関連項目

[起動と終了](../cpp/startup-and-termination-cpp.md)