# Atividade-DIO-Java
Singleton (Garante uma única instância de gerenciamento de configurações/banco).
# Projeto de Padrões de Projeto (Design Patterns) em Java Puro

Este repositório contém a implementação prática de Design Patterns fundamentais utilizando Java Puro, desenvolvido como projeto de conclusão de estudos sobre padrões de projeto.

## Padrões Aplicados
- **Singleton:** Utilizado para gerenciar configurações globais do sistema (`SingletonConfig`).
- **Strategy:** Utilizado para encapsular os algoritmos de cálculo de frete (`FreteStrategy`, `FreteNormal`, `FreteExpresso`).
- **Builder:** Utilizado para construção fluida e limpa de objetos complexos (`Pedido.Builder`).
git init
git add .
git commit -m "feat: adiciona implementação de Singleton, Strategy e Builder em Java Puro"
git branch -M main
git remote add origin <URL_DO_SEU_REPOSITORIO_NO_GITHUB>
git push -u origin main
package br.com.desafio.patterns;

public class SingletonConfig {
    
    private static SingletonConfig instancia;
    private String ambiente;

    // Construtor privado para evitar instanciamento externo
    private SingletonConfig() {
        this.ambiente = "PRODUÇÃO";
        System.out.println("[Singleton] Configurações do sistema carregadas com sucesso!");
    }

    public static synchronized SingletonConfig getInstancia() {
        if (instancia == null) {
            instancia = new SingletonConfig();
        }
        return instancia;
    }

    public String getAmbiente() {
        return ambiente;
    }
}
