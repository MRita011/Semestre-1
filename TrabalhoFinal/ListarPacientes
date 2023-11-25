/* A seguir, implemente uma Lista de Pacientes. Defina as operações necessárias para manipular essa lista.
 * método que cadastra pacientes na lista. O método deve garantir que nenhum paciente de mesmo nome e codigo sejam adicionados a lista de pacientes.
 * método que consulta um paciente por nome;
 * método que consulta um paciente por codigo;
 * método que mostra uma lista de todos os pacientes com idade acima de um valor informado pelo parâmetro;
 * método que lista todos os pacientes;
 * método que altera o peso de um determinado paciente, informando o seu código;
 * método que altera a altura de um determinado paciente, informando o seu código 
 * método que altera o sexo de um determinado paciente, informando seu código;
 * método que mostra o IMC de um determinado paciente.
 */

public class ListarPacientes
{
    private Paciente[] lista;
    private int proximoIndice;
    
    public ListarPacientes(int tamanho) {
        lista = new Paciente[tamanho];
        proximoIndice = 0;
    }

    // ------- MÉTODOS PARA VALIDAÇÃO ------- //
    public boolean validarNome(String nome) {
        // O nome do paciente não pode ser nulo
        if (nome != null && !nome.isEmpty()) 
            return true;

        else 
            return false;
    }

    public boolean validarPeso(double peso) {
        // O peso deve pertencer ao intervalo (0; 150kg]
        if (peso > 0 && peso <= 150)
            return true;

        else
            return false;
    }

    public boolean validarAltura(double altura) {
        // A altura deve respeitar o intervalo (0; 2,5m]
        if (altura > 0 && altura <= 2.5)
            return true;

        else
            return false;
    }

    public boolean validarIdade(double idade) {
        // a idade, [0; 120].
        if (idade >= 0 && idade <= 120)
            return true;

        else
            return false;
    }

    // ------- MÉTODOS PARA MANIPULAR A LISTA ------- //

    // Método que cadastra pacientes na lista. Garante que nenhum paciente do mesmo codigo/nome seja adicionado a lista
    public boolean cadastrarPaciente(Paciente p) {
        if (proximoIndice == 0) {
            lista[proximoIndice] = p;
            proximoIndice++;
            return true;
        }

        for (int i = 0; i < proximoIndice; i++) {
            if (lista[i].getCodigo() == p.getCodigo() && lista[i].getNome().equals(p.getNome())) {
                return false; // Paciente com mesmo código e nome já existe
            }
        }

        lista[proximoIndice] = p;
        proximoIndice++;
        return true;
    }

    // Método que consulta um paciente por nome
    public Paciente consultarPorNome(String nome){
        if (proximoIndice == 0)
            return null;

        for (int i = 0; i < proximoIndice; i++) {
            if (lista[i].getNome().equalsIgnoreCase(nome))
                return lista[i];
        }

        return null;
    }

    // Método que consulta um paciente por codigo
    public Paciente consultarPeloCodigo(int codigo) {
        if (proximoIndice == 0) 
            return null;
            
        for (int i = 0; i < proximoIndice; i++) {
            if (lista[i].getCodigo() == codigo)
                return lista[i];
        }
        return null; // não achou ninguém com esse código
    }

    // Método que mostra uma lista de todos os pacientes com idade acima de um valor informado pelo parâmetro;
    public int[] listarPacientesIdadeAcima(int idadeLimite) {
        int[] listaIdadeAcima = new int[proximoIndice];
        int proxInd = 0;

        for (int i = 0; i < proximoIndice; i++) {
            if (lista[i].getIdade() > idadeLimite) { // se o paciente da LISTA PACIENTES tiver uma idade maior do que o limite (parâmetro)
                listaIdadeAcima[proxInd] = lista[i].getCodigo();
                proxInd++;
            }
        }
        return listaIdadeAcima;
    }

    // método que lista todos os pacientes;
    public Paciente[] listarTodosPacientes() {
        Paciente[] todosPacientes = new Paciente[proximoIndice];

        for (int i = 0; i < proximoIndice; i++) {
            todosPacientes[i] = lista[i];
        }

        return todosPacientes;
    }

    //  método que altera o peso de um determinado paciente, informando o seu código;
    public boolean alterarPeso(double peso, int codigo) {
        Paciente pacienteAux = consultarPeloCodigo(codigo);

        if (pacienteAux != null) {
            pacienteAux.setPeso(peso); // chama o método set para atualizar o peso com o parâmetro
            return true;
        }

        else
            return false; // não achou ninguém com esse código
    }

    // método que altera a altura de um determinado paciente, informando o seu código;
    public boolean alterarAltura(double altura, int codigo) {
        Paciente pacienteAux = consultarPeloCodigo(codigo);

        if (pacienteAux != null) {
            pacienteAux.setAltura(altura);
            return true;
        }

        else
            return false; 
    }

    // método que altera o sexo de um determinado paciente, informando seu código;
    public boolean alterarSexo(char novoSexo, int codigo) {
        Paciente pacienteAux = consultarPeloCodigo(codigo);

        if (pacienteAux != null) {
            pacienteAux.setSexo(novoSexo);
            return true;
        }

        else
            return false; 
    }

    // método que mostra o IMC de um determinado paciente.
    public double mostrarIMC (int codigo) {
        Paciente pacienteAux = consultarPeloCodigo(codigo);

        if (pacienteAux != null)
            return pacienteAux.calcularIMC();

        return -1;
    }
}
