---
title: CRT へのリンクに使用する方法の利点とトレードオフ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1962b2db987e34a1f0d18fa863473a20f9da7c9d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084264"
---
# <a name="benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt"></a>CRT へのリンクに使用する方法の利点とトレードオフ

プロジェクトは、動的または静的に CRT でリンクできます。 次の表では、利点と使用する方法を選択する際にトレードオフについて説明します。

|メソッド|特長|トレードオフ|
|------------|-------------|--------------|
|CRT に静的にリンク<br /><br /> (**ランタイム ライブラリ**設定**シングル スレッド**)|イメージを実行するシステムでは、CRT DLL は必要はありません。|約 25 K のスタートアップ コードは、そのサイズを大幅に増やすこと、イメージに追加されます。|
|CRT に動的にリンク<br /><br /> (**ランタイム ライブラリ**設定**マルチ スレッド**)|イメージでは小さすぎるため、CRT のスタートアップ コードは必要ありません。|CRT DLL は、イメージを実行しているシステム上になければなりません。|

トピック[ATL プロジェクトで CRT にリンクする](../atl/linking-to-the-crt-in-your-atl-project.md)で CRT にリンクする方法を選択する方法について説明します。

## <a name="see-also"></a>関連項目

[ATL および C ランタイム コードによるプログラミング](../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[DLL と Visual C++ ランタイム ライブラリの動作](../build/run-time-library-behavior.md)<br/>
[CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)

