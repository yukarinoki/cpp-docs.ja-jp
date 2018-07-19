---
title: vtordisp |Microsoft ドキュメント
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
ms.openlocfilehash: 502425728fcd97d2ae8d2efe406dc73370de1272
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33841773"
---
# <a name="vtordisp"></a>vtordisp
**C 固有の仕様**  
  
 vtordisp 構築/破棄ディスプレイスメント隠しメンバーの追加を制御します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
#pragma vtordisp([push,] n)  
#pragma vtordisp(pop)  
#pragma vtordisp()  
#pragma vtordisp([push,] {on | off})  
```  
  
#### <a name="parameters"></a>パラメーター  
 `push`  
 現在の vtordisp 設定を内部コンパイラ スタックにプッシュし、新しい vtordisp 設定を `n` に設定します。  `n` が指定されていない場合、現在の vtordisp 設定は変更されません。  
  
 `pop`  
 内部コンパイラ スタックから先頭レコードを削除し、vtordisp 設定をその削除したレコードの値に戻します。  
  
 `n`  
 vtordisp 設定の新しい値を指定します。 有効値は 0、1 または 2 で、/vd0、/vd1、または /vd2 コンパイラ オプションに対応します。 詳細については、次を参照してください。 [/vd (無効にするディスプレイスメント)](../build/reference/vd-disable-construction-displacements.md)です。  
  
 `on`  
 これは、`#pragma vtordisp(1)` に相当します。  
  
 `off`  
 これは、`#pragma vtordisp(0)` に相当します。  
  
## <a name="remarks"></a>コメント  
 `vtordisp` プラグマは、仮想基底クラスを使用するコードだけに適用されます。 派生クラスが仮想基底クラスから継承する仮想関数をオーバーライドする場合、および派生クラスのコンストラクターやデストラクターが仮想基底クラスへのポインターを使用してその関数を呼び出す場合、コンパイラは仮想基底クラスを含むクラスに追加の `vtordisp` 隠しフィールドを導入する場合があります。  
  
 `vtordisp` プラグマは後続のクラス レイアウトに影響します。 /vd0、/vd1、および /vd2 オプションは、モジュール全体に同じ動作を指定します。 `0` または `off` を指定すると、`vtordisp` 隠しメンバーが抑制されます。 `vtordisp` は、クラスのコンストラクターとデストラクターが `this` ポインターによって指されるオブジェクトに対して仮想関数を呼び出す可能性がない場合にのみオフにします。  
  
 既定の `1` または `on` を指定すると、必要に応じて `vtordisp` 隠しメンバーが有効になります。  
  
 指定する`2`、非表示を有効に`vtordisp`仮想関数を持つすべての仮想ベースのメンバーです。  `vtordisp(2)` パフォーマンスが正しいことを確認する必要があります`dynamic_cast`部分的に構築されるオブジェクト。 詳細については、次を参照してください。[コンパイラの警告 (レベル 1) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)です。  
  
 引数のない `#pragma vtordisp()` は、vtordisp 設定を初期設定に戻します。  
  
```  
#pragma vtordisp(push, 2)  
class GetReal : virtual public VBase { ... };  
#pragma vtordisp(pop)  
```  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)