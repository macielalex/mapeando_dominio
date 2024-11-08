# mapeando_dominio


inventory-management-system/
src/                                # Diretório principal do código-fonte
    application/                    # Camada de aplicação (casos de uso e interfaces)
        use-cases/                  # Diretório para os casos de uso
            RastreamentoProduto/    # Caso de uso: rastrear produto
                RastreamentoProdutoUseCase.ts
                RastreamentoProdutoDTO.ts  # DTO para entrada/saída
            DefinirQuantidadeMinima/
                DefinirQuantidadeMinimaUseCase.ts
                DefinirQuantidadeMinimaDTO.ts
            ...                     # Outros casos de uso
        interfaces/                 # Interfaces para comunicação entre camadas
            ProdutoRepository.ts
            EstoqueRepository.ts
            NotificationService.ts

    domain/                         # Camada de domínio
        entities/                   # Entidades do domínio
            Produto.ts              # Entidade Produto
            Estoque.ts              # Entidade Estoque
            HistoricoVendas.ts      # Entidade Histórico de Vendas
            OrdemCompra.ts          # Entidade Ordem de Compra
            Fornecedor.ts           # Entidade Fornecedor
        value-objects/              # Objetos de valor
            ProdutoID.ts
            QuantidadeMinima.ts
            ...                     # Outros objetos de valor

    infrastructure/                 # Camada de infraestrutura
        persistence/                # Repositórios de dados
            ProdutoRepositoryImpl.ts # Implementação do repositório de Produto
            EstoqueRepositoryImpl.ts # Implementação do repositório de Estoque
            ...                     # Outros repositórios
        notification/               # Implementação do serviço de notificação
            EmailNotifier.ts        # Serviço de notificação por e-mail
            SystemNotifier.ts       # Serviço de notificação por sistema
        database/                   # Configuração e models do banco de dados
            dbConfig.ts             # Configuração do banco de dados
            models/                 # Models para interação com o banco
                ProdutoModel.ts
                EstoqueModel.ts
                ...
        http/                       # Configuração de rotas e controladores
            routes/                 # Rotas da API
                produtoRoutes.ts    # Rotas para produtos
                ordemCompraRoutes.ts # Rotas para ordens de compra
                ...
            controllers/            # Controladores de cada rota
                ProdutoController.ts # Controlador para produtos
                OrdemCompraController.ts # Controlador para ordens de compra
                ...

    shared/                         # Código compartilhado entre camadas
        errors/                     # Classes de erros customizados
            AppError.ts             # Classe base para erros
        utils/                      # Utilitários gerais
        types/                      # Tipos e interfaces globais
            index.ts

    config/                         # Configurações globais do projeto
        default.ts                  # Configurações de ambiente

tests/                              # Diretório para testes
    application/                    # Testes da camada de aplicação
    domain/                         # Testes da camada de domínio
    infrastructure/                 # Testes da camada de infraestrutura
    integration/                    # Testes de integração

.env                                # Variáveis de ambiente
.gitignore                          # Arquivo Gitignore
package.json                        # Dependências e scripts do projeto
tsconfig.json                       # Configuração do TypeScript
README.md                           # Documentação do projeto
