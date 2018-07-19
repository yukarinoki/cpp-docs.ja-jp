---
title: 相互運用 (C++) のパフォーマンスに関する考慮事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- /clr compiler option [C++], interop performance considerations
- platform invoke [C++], interoperability
- interop [C++], performance consideraitons
- mixed assemblies [C++], performance considerations
- interoperability [C++], performance considerations
ms.assetid: bb9a282e-c3f8-40eb-a2fa-45d80d578932
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9223c52e4ef831a9a1ff657db1a0d7859dd6ce6c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164051"
---
# <a name="performance-considerations-for-interop-c"></a>Interop (C++) のパフォーマンスに関する考慮事項
このトピックでは、実行時のパフォーマンス上の相互運用機能の遷移をマネージ/アンマネージの影響を軽減するためのガイドラインを提供します。  
  
 Visual C は、Visual Basic および C# の場合 (P/invoke) などの他の .NET 言語との相互運用性と同じメカニズムをサポートしていますが、Visual C (C++ interop) に固有である相互運用機能のサポートも提供します。 パフォーマンスが重要なアプリケーションの場合に、各相互運用の手法のパフォーマンスの影響について理解する必要があります。  
  
 相互運用機能の手法を使用してに関係なく、サンクと呼ばれる特別な遷移シーケンスは必要なたびにマネージ関数を呼び出す、アンマネージ関数およびその逆です。 これらサンクは、Visual C コンパイラで自動的に挿入されますが、累積的に、このような移行できるパフォーマンスの観点から高価なに留意することが重要です。  
  
## <a name="reducing-transitions"></a>遷移の削減  
 回避またはサンクの相互運用機能のコストを削減する方法の 1 つをマネージ/アンマネージの遷移を最小限に関連するインターフェイスのリファクタリングを開始します。 大幅なパフォーマンス強化 chatty なインターフェイスは、マネージ/アンマネージの境界を越えての呼び出し頻度を関係している対象にします。 タイト ループでアンマネージ関数を呼び出すマネージ関数では、リファクタリングの適切な候補などです。 ループ自体は、アンマネージ側に移動したり、アンマネージ呼び出しを作成する代わりに管理されている場合 (おそらくをマネージ側キュー データとして使用して、マーシャ リング、アンマネージ API に、ループの後に、一度に)、遷移の数は、記号の削減ificantly です。  
  
## <a name="pinvoke-vs-c-interop"></a>P/invoke vs です。C++ Interop  
 Visual Basic および C# の場合などの .NET 言語では、ネイティブ コンポーネントとの相互運用の所定の方法は P/invoke です。 P/invoke は .NET Framework でサポートされているため、Visual C がサポートされてが、Visual C には、C++ Interop と呼びますの独自の相互運用性サポートも用意されています。 C++ Interop は、P/invoke がタイプ セーフではないために、P/invoke を優先します。 その結果、実行時にエラーが報告される、主に C++ Interop も利点がありますパフォーマンス P/invoke 経由でします。  
  
 両方の手法には、マネージ関数は、アンマネージ関数を呼び出す際に、次の点が必要です。  
  
-   関数呼び出しの引数は、ネイティブ型に CLR からマーシャ リングされます。  
  
-   マネージ、アンマネージ サンクが実行されます。  
  
-   (引数のネイティブ バージョンを使用)、アンマネージ関数が呼び出されます。  
  
-   アンマネージからマネージへのサンクが実行されます。  
  
-   戻り値の型と"out"または"で、アウト"引数は CLR 型をネイティブ コードからマーシャ リングします。  
  
 マネージ/アンマネージ サンクは、相互運用のすべての作業が、関連するデータ型、関数シグネチャ、およびデータの使用方法によって異なりますが必要なデータのマーシャ リングします。  
  
 C++ 相互運用機能によって実行されるデータのマーシャ リング可能な最も単純な形式は、: パラメーターは; ビットごとの方法でマネージ/アンマネージの境界を越えてコピーされるだけです変換は実行されませんでします。 P/invoke では、これはすべてのパラメーターは、単純な場合は true。 blittable 型です。 P/invoke が各管理対象のパラメーターを適切なネイティブ型に変換する非常に堅牢な手順を実行するそれ以外の場合、引数が"out"としてマークされている場合にその逆の場合、または"で、アウト"です。  
  
 つまり、C++ Interop 使われます。 データのマーシャ リングでの最も速い方法 P/invoke は最も堅牢なメソッドを使用します。 つまり、C++ Interop (C++ の標準的な方法) では、既定では、最適なパフォーマンスを提供および、プログラマがこの動作が行われていない安全なまたは適切な場合に対応します。  
  
 したがって、C++ 相互運用するには、データのマーシャ リングし、明示的に指定する必要がありますが、利点は、プログラマは、データの性質に応じて、適切なとが使用する方法を決定することが必要です。 さらに、P/invoke データのマーシャ リングの動作は、ある程度カスタマイズで変更できます、C++ Interop できますデータ マーシャ リングの呼び出しによってごとにカスタマイズできます。 これは、P/invoke では可能ではありません。  
  
 C++ 相互運用機能の詳細については、次を参照してください。[を使用して C++ Interop (暗黙の PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)です。  
  
## <a name="see-also"></a>関連項目  
 [混在 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)