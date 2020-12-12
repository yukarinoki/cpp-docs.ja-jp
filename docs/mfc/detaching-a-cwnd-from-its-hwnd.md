---
description: 詳細については、「CWnd を HWND からデタッチする」を参照してください。
title: CWnd と HWND の分離
ms.date: 11/04/2016
helpviewer_keywords:
- HWND, detaching CWnd from
- removing HWNDs from CWnds
- CWnd objects [MFC], detaching from HWND
- detaching CWnds from HWNDs
- Detach method (CWnd class)
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
ms.openlocfilehash: a3bb1c50b769724ff9ea0f7cdcd2d1fa92cb3a84
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327803"
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>CWnd と HWND の分離

オブジェクトの関係を回避する必要がある場合は、 `HWND` MFC によって別のメンバー関数 Detach が提供され、 `CWnd` Windows ウィンドウから C++ ウィンドウオブジェクトが切断されます。 [](reference/cwnd-class.md#detach) これにより、オブジェクトが破棄されたときに、デストラクターが Windows ウィンドウを破棄するのを防ぎます。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ウィンドウの作成](creating-windows.md)

- [ウィンドウの破棄順序](window-destruction-sequence.md)

- [ウィンドウ メモリの割り当てと解放](allocating-and-deallocating-window-memory.md)

## <a name="see-also"></a>関連項目

[ウィンドウオブジェクト](window-objects.md)
