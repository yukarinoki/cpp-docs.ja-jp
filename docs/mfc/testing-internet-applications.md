---
description: 詳細については、「インターネットアプリケーションのテスト」を参照してください。
title: インターネット アプリケーションのテスト
ms.date: 11/04/2016
helpviewer_keywords:
- Web applications [MFC], testing
- debugging Web applications [MFC], testing applications
- testing [MFC], Internet applications
- debugging [MFC], Web applications
- Internet debugging and testing
ms.assetid: ac4c74e3-d4ad-4e19-8f6c-e270de067f01
ms.openlocfilehash: ed3dd9819524e156af47da4070c517e3761380ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216263"
---
# <a name="testing-internet-applications"></a>インターネット アプリケーションのテスト

インターネットには、特に Web サーバーで実行されているアプリケーションに対して、独自のテストの課題がいくつかあります。 最初のテストは、テストサーバーに接続しているシングルユーザークライアントを使用して行われる可能性があります。 これは、コードのデバッグに役立ちます。

また、実際の状況下でもテストする必要があります。高速接続を使用して複数のクライアントを接続し、モデム接続を含む低速のシリアル回線を使用します。 実際の状況をシミュレートするのは困難な場合がありますが、考えられるシナリオの設計と実行に時間を費やす価値があります。 可能であれば、ツールを使用して容量とストレステストを実行することもできます。 タイミングバグなど、バグの特定のクラスを見つけて再現するのは困難です。

インターネットプログラミングの課題の1つに、その可視性があります。 サイトへのアクセスが多くなると、サーバーの速度が低下する可能性があります。 サーバーのパフォーマンスが適切に低下します。 アプリケーションでエラーが発生した場合 (レジストリへの書き込み中やクライアントでの cookie の書き込み中にデータが破損した場合など)、ユーザーのコンピューターに破壊的なことを防ぐ必要があります。

## <a name="see-also"></a>関連項目

[MFC インターネットプログラミングタスク](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC インターネットプログラミングの基礎](../mfc/mfc-internet-programming-basics.md)
