---
title: Abrufen eines einzelnen Werts aus einer Datenbank
description: Erfahren Sie, wie Sie einen einzelnen Wert in ADO.net zurückgeben. Dieser Beispielcode gibt den Identitäts Spaltenwert für einen eingefügten Datensatz zurück.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: a6f268f72f8b8a09ae48ba3cad6254323cb95a20
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286701"
---
# <a name="obtaining-a-single-value-from-a-database"></a>Abrufen eines einzelnen Werts aus einer Datenbank
Es kann vorkommen, dass Sie lediglich einzelne Werte anstelle von Tabellen oder Datenstreams aus einer Datenbank zurückgeben möchten. Beispielsweise können Sie das Ergebnis einer Aggregatfunktion wie count ( \* ), Sum (Price) oder AVG (Menge) zurückgeben. Das **Command** -Objekt bietet die Möglichkeit, einzelne Werte mithilfe der **ExecuteScalar** -Methode zurückzugeben. Die **ExecuteScalar** -Methode gibt den Wert der ersten Spalte der ersten Zeile des Resultsets als Skalarwert zurück.  
  
 Im folgenden Codebeispiel wird mit einem <xref:System.Data.SqlClient.SqlCommand> ein neuer Wert in der Datenbank eingefügt. Mit der <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A>-Methode wird der Wert der Identitätsspalte für den eingefügten Datensatz zurückgegeben.  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Befehle und Parameter](commands-and-parameters.md)
- [Ausführen eines Befehls](executing-a-command.md)
- ["DbConnection", "DbCommand" und "DbException"](dbconnection-dbcommand-and-dbexception.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
