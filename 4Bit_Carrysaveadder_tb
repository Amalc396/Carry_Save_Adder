`timescale 1ns/1ps

module tb_csavea;
    reg [3:0] x, y, z;       
    wire [4:0] s;            
    wire cout;               
    integer i, j, k, error;  
    csavea uut (
        .x(x),
        .y(y),
        .z(z),
        .s(s),
        .cout(cout)
    );
    initial begin
        x = 0;
        y = 0;
        z = 0;
        error = 0;
        $dumpfile("csavea_wave.vcd");    
        $dumpvars(0, tb_csavea);        

        
        $monitor("Time=%0t | x=%d | y=%d | z=%d | s=%d | cout=%b | error=%d", 
                 $time, x, y, z, s, cout, error);

        
      for (i = 0; i < 10; i = i + 1) begin
        for (j = 0; j < 10; j = j + 1) begin
          for (k = 0; k < 10; k = k + 1) begin
                    x = i;         
                    y = j;          
                    z = k;         
                    #10;            
                    if ({cout, s} != (i + j + k)) begin
                        error = error + 1;  
                    end
                end
            end
        end

        
        #10; 
        $display("Simulation finished. Total errors: %d", error);
        $finish;  
    end

endmodule
