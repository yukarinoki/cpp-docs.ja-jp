---
title: vtordisp |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.vtordisp
- vtordisp_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, vtordisp
- vtordisp pragma
ms.assetid: 05b7d73c-43fa-4b62-8c8a-170a9e427391
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5d0b28c855ab8a6f6da814ee17521a5ad7799993
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2018
ms.locfileid: "42539035"
---
# <a name="vtordisp"></a>vtordisp
**C++ 固有の仕様**  
  
vtordisp 構築/破棄ディスプレイスメント隠しメンバーの追加を制御します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
#pragma vtordisp([push,] n)  
#pragma vtordisp(pop)  
#pragma vtordisp()  
#pragma vtordisp([push,] {on | off})  
```  
  
### <a name="parameters"></a>パラメーター  
*push*  
現在の vtordisp 設定を内部コンパイラ スタックにプッシュし、新しい vtordisp 設定を設定*n*します。  場合*n*が指定されていない、現在の vtordisp 設定は変更されません。  
  
*pop*  
内部コンパイラ スタックから先頭レコードを削除し、vtordisp 設定をその削除したレコードの値に戻します。  
  
*n*  
vtordisp 設定の新しい値を指定します。 指定できる値は 0、1 または 2 に対応する、 `/vd0`、 `/vd1`、および`/vd2`コンパイラ オプション。 詳細については、次を参照してください。 [/vd (ディスプレイスメント)](../build/reference/vd-disable-construction-displacements.md)します。  
  
*on*  
これは、`#pragma vtordisp(1)` に相当します。  
  
*オフ*  
これは、`#pragma vtordisp(0)` に相当します。  
  
## <a name="remarks"></a>Remarks  
 
**Vtordisp**プラグマが仮想基底クラスを使用するコードにのみ適用されます。 派生クラスが仮想基底クラスから継承する仮想関数をオーバーライドし、コンス トラクターまたは派生クラスのデストラクターが仮想基底クラスへのポインターを使用してその関数を呼び出す場合、コンパイラが追加の非表示を導入可能性があるかどうか**vtordisp**仮想基底クラスへのフィールド。  
  
**Vtordisp**プラグマが後続のクラスのレイアウトに影響します。 `/vd0`、 `/vd1`、および`/vd2`オプションは、モジュール全体に同じ動作を指定します。 0 を指定するか、*オフ*、非表示を抑制します**vtordisp**メンバー。 オフにする**vtordisp**が指すオブジェクトのクラスのコンス トラクターとデストラクターを呼び出す仮想可能性が機能しないがある場合のみ、**この**ポインター。  
  
1 を指定するまたは*で*を既定で有効隠し**vtordisp**メンバーの依存関係が必要です。  
  
2 では、非表示を指定する**vtordisp**仮想関数を持つすべての仮想基底クラスのメンバー。  `vtordisp(2)` 適切なパフォーマンスを確保する必要があります**dynamic_cast**部分的に構築されたオブジェクト。 詳細については、次を参照してください。[コンパイラの警告 (レベル 1) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)します。  
  
引数のない `#pragma vtordisp()` は、vtordisp 設定を初期設定に戻します。  
  
```  
#pragma vtordisp(push, 2)  
class GetReal : virtual public VBase { ... };  
#pragma vtordisp(pop)  
```  
  
**END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 
[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)