---
title: 起動に関するその他の考慮事項
ms.date: 11/04/2016
helpviewer_keywords:
- program startup [C++]
- startup code
- initializing before main
ms.assetid: 0e942aa6-8342-447c-b068-8980ed7622bd
ms.openlocfilehash: 16e48f2e4f7544d28a1bea00e1fdf2d1cff397b5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385077"
---
# <a name="additional-startup-considerations"></a>起動に関するその他の考慮事項

C++ では、オブジェクトの構築時と破棄時にユーザーコードを実行することができます。 したがって、`main` に入る前にどのような初期化が発生するかと `main` から抜けた後にどのデストラクターが呼び出されるを分かっておく事は重要です。(オブジェクトの構築と破棄の詳細については、[コンストラクター](../cpp/constructors-cpp.md)と[デストラクター](../cpp/destructors-cpp.md)を参照してください。)

`main` に入る前に後述する初期化が行われます:

- 静的データのゼロへのデフォルトの初期化。 明示的な初期化子のないすべての静的データはどんなコード（ランタイム初期化も含む）を実行する前にもゼロに設定されます。 静的データメンバーはその場合でも明示的に定義する必要があります。

- 翻訳単位でのグローバルな静的オブジェクトの初期化。 `main` に入る前または翻訳単位内の関数やオブジェクトがどれでも初めて使用される前に行われます。

**Microsoft 固有の仕様**

Microsoft C では、`main` に入る前にグローバルな静的オブジェクトが初期化されます。

**Microsoft 固有の仕様はここまで**

相互依存しているのに翻訳単位が異なるグローバルな静的オブジェクトは、正しくない動作の原因になる可能性があります。

## <a name="see-also"></a>関連項目

[起動と終了](../cpp/startup-and-termination-cpp.md)