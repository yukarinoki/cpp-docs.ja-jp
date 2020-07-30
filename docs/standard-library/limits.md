---
title: '&lt;limits&gt;'
ms.date: 11/04/2016
f1_keywords:
- limits/std::<limits>
- <limits>
helpviewer_keywords:
- limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
ms.openlocfilehash: 2d0f4f96d25c91ac20fe5a1883fc61fc47d15d5e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217689"
---
# <a name="ltlimitsgt"></a>&lt;limits&gt;

クラステンプレートと、 `numeric_limits` 浮動小数点の表現と丸め処理に関する2つの列挙体を定義します。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<limits>

**名前空間:** std

## <a name="remarks"></a>解説

クラスの明示的な特殊化には、 `numeric_limits` 文字、整数、浮動小数点型など、基本型の多くのプロパティが記述さ **`bool`** れています。これは、C++ 言語の規則ではなく、定義された実装です。 「」で説明されているプロパティに \<limits> は、精度、最小および最大サイズの表現、丸め、およびシグナリングの種類のエラーが含まれます。

## <a name="members"></a>メンバー

### <a name="enumerations"></a>列挙型

|||
|-|-|
|[float_denorm_style](../standard-library/limits-enums.md#float_denorm_style)|この列挙体では、小さすぎて、正規化された値としては表現できない非正規化された浮動小数点値を表現するために、実装で選択できるさまざまなメソッドを記述します。|
|[float_round_style](../standard-library/limits-enums.md#float_round_style)|この列挙体では、浮動小数点値を整数値に丸めるために、実装で選択できるさまざまなメソッドを記述します。|

### <a name="classes"></a>クラス

|||
|-|-|
|[numeric_limits クラス](../standard-library/numeric-limits-class.md)|クラステンプレートでは、組み込みの数値型の算術プロパティについて説明します。|

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
