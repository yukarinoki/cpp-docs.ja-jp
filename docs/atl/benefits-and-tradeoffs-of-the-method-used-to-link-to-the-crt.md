---
description: 詳細については、「CRT へのリンクに使用される方法の利点とトレードオフ」を参照してください。
title: CRT へのリンクに使用される方法の利点とトレードオフ
ms.date: 05/06/2019
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
ms.openlocfilehash: 763332de9615e978d84902f67f2c97efd0767c89
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148526"
---
# <a name="benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt"></a>CRT へのリンクに使用される方法の利点とトレードオフ

プロジェクトは、動的または静的に CRT とリンクできます。 次の表は、使用する方法の選択に関連する利点とトレードオフの概要を示しています。

|Method|特長|トレードオフ|
|------------|-------------|--------------|
|CRT に静的にリンクする<br /><br /> (**ランタイムライブラリ** が **シングルスレッド** に設定される)|イメージを実行するシステムでは、CRT DLL は必要ありません。|25,000 のスタートアップコードの概要がイメージに追加され、サイズが大幅に増加しています。|
|CRT に動的にリンクする<br /><br /> (**ランタイムライブラリ** が **マルチスレッド** に設定される)|イメージは CRT スタートアップコードを必要としないため、はるかに小さくなります。|CRT DLL は、イメージを実行しているシステム上にある必要があります。|

[ATL プロジェクトの crt へ](../atl/linking-to-the-crt-in-your-atl-project.md)のリンクに関するトピックでは、crt にリンクする方法を選択する方法について説明します。

## <a name="see-also"></a>関連項目

[ATL および C Run-Time コードを使用したプログラミング](../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[DLL と Visual C++ ランタイム ライブラリの動作](../build/run-time-library-behavior.md)<br/>
[CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)
